# Spending credits deliberately

## What is free

`get_balance`, `find-tools`, `inspect-tool`, `preview`, and `list_collections`
never deduct. A tool whose preview comes back `"workflow": "complete"` is free
too, and the data is already in the preview response.

## What bills

`confirm`, `call-tool`, and any direct `search-<name>` call. The first is
deliberate; the other two are immediate. Prefer the deliberate path unless the
user has already said yes to the spend.

## Unlock only what is relevant

For search previews, the teaser carries every result's metadata (title,
publisher, year, source) and a short snippet per chunk. Read them, pick the
results that actually answer the question, and pass only those ids:

```
confirm { "preview_id": "...", "result_ids": ["r1", "r4"] }
```

Omitting `result_ids` unlocks everything and bills for everything. That is
rarely what the user wants from a ten-result preview.

## Re-use instead of re-search

A search response includes a `query_id`. The same results can be fetched again
with it, free, for seven days. If the user asks a follow-up against the same
material, re-fetch rather than running and paying for the search again.

## Balance

`confirm` returns `cost_charged` and `balance_remaining`. Report both; a second
`get_balance` call is unnecessary. When the server's instructions carry a
low-balance warning, quote the remaining balance next to every cost so the user
can decide with the number in front of them.

## Trial

A trial account has a fixed number of queries rather than a balance. Previews
do not consume them; confirmed or direct calls do. The server's instructions
say how many remain. Be explicit that a direct `search-<name>` call spends one.

## Expired preview

Previews last ten minutes. A `confirm` after that returns an error; re-run the
`preview` and confirm the fresh one. The user is not charged for the expired
attempt.
