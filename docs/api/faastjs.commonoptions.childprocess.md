---
id: faastjs.commonoptions.childprocess
title: CommonOptions.childProcess property
hide_title: true
---
[faastjs](./faastjs.md) &gt; [CommonOptions](./faastjs.commonoptions.md) &gt; [childProcess](./faastjs.commonoptions.childprocess.md)

## CommonOptions.childProcess property

If true, create a child process to isolate user code from faast scaffolding. Default: true.

<b>Signature:</b>

```typescript
childProcess?: boolean;
```

## Remarks

If a child process is not created, faast runs in the same node instance as the user code and may not execute in a timely fashion because user code may [block the event loop](https://nodejs.org/en/docs/guides/dont-block-the-event-loop/)<!-- -->. Creating a child process for user code allows faast.js to continue executing even if user code never yields. This provides better reliability and functionality:

- Detect timeout errors immediately instead of waiting for the provider's dead letter queue messages, which may take several minutes. See [CommonOptions.timeout](./faastjs.commonoptions.timeout.md)<!-- -->.

- CPU metrics used for detecting invocations with high latency, which can be used for automatically retrying calls to reduce tail latency.

The cost of creating a child process is mainly in the memory overhead of creating another node process.