# When something does not work

## The tool is not in the catalog

Not an error. The catalog is generated per account from its entitlements, so
an absent tool means the account cannot reach that data. Say which vertical is
missing and let the user decide. Do not retry, do not route around it through
another tool, and do not answer from training data as though it came from
Redpine.

If the user has just purchased or been granted access and it still is not
listed, the session predates the change. A running client keeps the tool list
it received when it connected; they need to reconnect.

## No balance left

Paid tools stop working when the balance is exhausted, and so does `preview`.
Free tools continue. The server states this in its own instructions together
with the correct dashboard URL for that account. Use that URL, and never
construct one from the brand name.

Say the balance is exhausted, say which part of the request that blocks, and
deliver whatever the free tools can still answer.

## The preview looks expensive

Show the number before confirming, not after. If several results are available
and only some are relevant, unlock those alone with `result_ids`. When the
server has warned that the balance is low, quote the remaining balance next to
the cost.

## The call returned nothing

An empty result is a finding. Report it as one.

Before calling it a dead end, check the cheap explanations: an over-narrow
window, a place name that needed a code, an entity that matched nothing for
spelling or jurisdiction. Change one thing and try at most once more. Repeating
the same call unchanged spends money for the same answer.

## The call errored

Read the error rather than retrying. A schema complaint means parameters were
guessed; go back to `inspect-tool`. A session or authentication error means
the connection needs re-establishing, which is the user's action. Surface the
error text; do not paraphrase it into something vaguer.
