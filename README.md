# HAMT CRDT

HAMT CRDT is an infinitely scalable key-value store that is implemented as
a HAMT data structure and a CRDT. Each HAMT node stores up to 16 *key-value-time*
3-tuple entries and up to 17 links to child nodes.

It supports "put" and "delete" operations operation. To delete a key, one puts an
`undefined` value. Each operation is accompanied by an ID (timestamp), expressed
as Hybrid Logical Clock (HLC) value. Each key is a single value LWW register,
where the HLC clock is used determining the winner.
