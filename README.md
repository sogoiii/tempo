# Tempo

### A tool to simplify time management in EVM Tests

The problem: there are different APIs for traversing time in tests that run against TestRPC as well as a 'regular' EVM.

Tempo provides a simple interface for 'fast-forwarding' time (mining blocks) that will transparently fallback to regular mining when TestRPC is not available.

## Usage

```javascript
// pass web3 instance to tempo
const tempo = new Tempo(web3);

// API for both TestRPC and regular RPC
tempo.toBlock(n); // mine until we hit this block number
tempo.waitFor(n); // mine for x number of blocks
tempo.currentBlock;

// API for TestRPC only
tempo.toBlock(n, timestamp);
tempo.waitFor(n, timestamp);
tempo.snapshot('snapshotId');
tempo.restore('snapshotId');
```

## Tests

`npm run test`

## License

MIT 2016