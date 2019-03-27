# Goggle Summer of Code Ideas

## Non-functional Requirements
Work alongside seasoned developers to help with performance testing, penetration testing for security and improving quality.
These are not trivial with a system like ours - and you were learn tons about financial systems and benchmarking.

## Retry Logic
As in financial system it is critical that there is the right level of retry logic throughout our system.  This can be in person to person payments or in the settlements.  We want to make sure that there is significant retry logic from the Switch that helps retrying for HTTP calls that do not receive a 2xx HTTP response code. Not all error codes should be retried, and such things should be part of that design and implementations.

## Loss Recovery
Help to design and implement the start-up logic after a wipe-out or a catastrophic-loss. There must be some kind of handler that deals with in-progress transactions, instead of just timing them all out. This needs good amount of designing and discussions, so bring your thinking cap.

