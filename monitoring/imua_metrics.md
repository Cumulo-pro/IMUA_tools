# Imua Documentation

## Table of Contents
1. [Block Interval Time](#block-interval-time)
    - [Block Interval Time Sum](#block-interval-time-sum)
    - [Block Interval Time Count](#block-interval-time-count)
    - [Block Interval Average](#block-interval-average)
2. [Block Parts Transmitted by Peer](#block-parts-transmitted-by-peer)
3. [Block Size](#block-size)
4. [Block Syncing Status](#block-syncing-status)
5. [Byzantine Validators Count](#byzantine-validators-count)
6. [Byzantine Validators Power](#byzantine-validators-power)
7. [Full Prevote Delay](#full-prevote-delay)
8. [Chain Height](#chain-height)
9. [Late Votes](#late-votes)
10. [Number of Missing Validators](#number-of-missing-validators)
11. [Missing Validators Power](#missing-validators-power)
12. [Number of Transactions](#number-of-transactions)
13. [Proposal Receive Count](#proposal-receive-count)
14. [State Syncing Status](#state-syncing-status)
15. [Total Transactions](#total-transactions)
16. [Last Signed Height (Validator)](#last-signed-height-validator)
17. [Missed Blocks (Validator)](#missed-blocks-validator)
18. [Validator Power](#validator-power)
19. [Number of Validators](#number-of-validators)
20. [Total Validators Power](#total-validators-power)
21. [Active Outbound Connections in Mempool](#active-outbound-connections-in-mempool)
22. [Mempool Recheck Count](#mempool-recheck-count)
23. [Mempool Size](#mempool-size)
24. [Mempool Size in Bytes](#mempool-size-in-bytes)
25. [P2P Message Received Bytes](#p2p-message-received-bytes)
26. [P2P Message Sent Bytes](#p2p-message-sent-bytes)
27. [Number of Peers](#number-of-peers)
28. [Block Processing Time](#block-processing-time)
29. [Validator Set Updates](#validator-set-updates)
30. [Consensus Parameter Updates](#consensus-parameter-updates)
31. [Go Garbage Collection Duration](#go-garbage-collection-duration)
32. [Goroutines Count](#goroutines-count)
33. [Process CPU Seconds Total](#process-cpu-seconds-total)
34. [Process Resident Memory Bytes](#process-resident-memory-bytes)

______________________________________

## Block Interval Time
- **Metric**: `cometbft_consensus_block_interval_seconds`
- **Description**: Indicates the time elapsed between the current and the last block. This histogram metric provides data segmented into various time intervals (e.g., <=0.005, <=0.01 seconds). Useful for understanding the consistency of block generation intervals and detecting delays in block production.

### Metric Variants

### Block Interval Time Sum
- **Metric**: `cometbft_consensus_block_interval_seconds_sum`
- **Description**: Represents the cumulative time elapsed between blocks since monitoring started. Useful for calculating the average time between blocks when combined with count.

### Block Interval Time Count
- **Metric**: `cometbft_consensus_block_interval_seconds_count`
- **Description**: Indicates the total number of recorded block intervals. Useful for verifying the regularity of block production and ensuring the node consistently registers blocks. Essential for calculating the average block interval and checking production frequency.

### Block Interval Average
- **Description**: Represents the calculated average time between blocks by dividing the sum by the count, offering insights into block production speed over time.

## Additional Metrics

### Block Parts Transmitted by Peer
- **Metric**: `cometbft_consensus_block_parts`
- **Description**: Shows the number of block parts sent by each peer in the network, identified by peer_id. Allows monitoring the distribution of block parts, which can help identify network traffic patterns or potential issues in data sharing between peers.

### Block Size
- **Metric**: `cometbft_consensus_block_size_bytes`
- **Description**: Measures the size of the most recent block in bytes. Provides insights into block capacity usage, which can be useful for understanding the volume of data processed per block.

### Block Syncing Status
- **Metric**: `cometbft_consensus_block_syncing`
- **Description**: Indicates whether the node is currently syncing blocks. Displays 1 if syncing, 0 if not. Helps diagnose the synchronization status, allowing operators to confirm if the node is up-to-date.

### Byzantine Validators Count
- **Metric**: `cometbft_consensus_byzantine_validators`
- **Description**: Shows the count of validators that attempted to double-sign or engage in other byzantine behavior. Aids in identifying malicious validators in the network.

### Byzantine Validators Power
- **Metric**: `cometbft_consensus_byzantine_validators_power`
- **Description**: Displays the total power of validators involved in byzantine behavior. Highlights the impact of byzantine validators based on their total voting power.

### Full Prevote Delay
- **Metric**: `cometbft_consensus_full_prevote_delay`
- **Description**: Measures the time interval between the proposal timestamp and the timestamp of the latest prevote in a round where all validators have voted, segmented by proposer_address. Helps track and optimize the consensus round timing.

### Chain Height
- **Metric**: `cometbft_consensus_height`
- **Description**: Displays the current height of the chain. Useful for confirming node progress and ensuring it is in sync with the network.

### Late Votes
- **Metric**: `cometbft_consensus_late_votes`
- **Description**: Shows the count of votes received by the node that correspond to earlier heights and rounds than the current state, categorized by vote type (prevote or precommit). Allows monitoring of late votes, which can help diagnose potential network latency or communication issues.

### Number of Missing Validators
- **Metric**: `cometbft_consensus_missing_validators`
- **Description**: Represents the number of validators that failed to sign the latest block. Aids in identifying validator participation and availability issues.

### Missing Validators Power
- **Metric**: `cometbft_consensus_missing_validators_power`
- **Description**: Shows the total power of validators that did not sign the latest block. Highlights the influence of missing validators on network consensus based on their voting power.

### Number of Transactions
- **Metric**: `cometbft_consensus_num_txs`
- **Description**: Displays the number of transactions included in the current block. Offers insight into network activity and transaction throughput.

### Proposal Receive Count
- **Metric**: `cometbft_consensus_proposal_receive_count`
- **Description**: Shows the count of proposals received by the node since its start, categorized by status (accepted or rejected). Useful for tracking proposal processing rates and success rates of proposals.

### State Syncing Status
- **Metric**: `cometbft_consensus_state_syncing`
- **Description**: Indicates if the node is currently state syncing. Displays 1 if syncing, 0 if not. Helps diagnose the state sync status, allowing operators to confirm if the node is up-to-date.

### Total Transactions
- **Metric**: `cometbft_consensus_total_txs`
- **Description**: Shows the total number of transactions processed by the node. Offers an overview of the transaction throughput, indicating network activity levels.

### Last Signed Height (Validator)
- **Metric**: `cometbft_consensus_validator_last_signed_height`
- **Description**: Displays the last block height signed by the validator. Useful for tracking validator activity and confirming timely participation.

### Missed Blocks (Validator)
- **Metric**: `cometbft_consensus_validator_missed_blocks`
- **Description**: Indicates the number of blocks missed by the validator. Helps monitor validator reliability and can signal issues with validator performance.

### Validator Power
- **Metric**: `cometbft_consensus_validator_power`
- **Description**: Shows the voting power of a specific validator. Provides insights into the influence of a validator within the network, based on its assigned voting power.

### Number of Validators
- **Metric**: `cometbft_consensus_validators`
- **Description**: Represents the total number of validators in the network. Useful for monitoring the size of the validator set.

### Total Validators Power
- **Metric**: `cometbft_consensus_validators_power`
- **Description**: Indicates the cumulative voting power of all validators. Helps gauge the overall security and decentralization of the network.

### Active Outbound Connections in Mempool
- **Metric**: `cometbft_mempool_active_outbound_connections`
- **Description**: Shows the number of connections actively used for gossiping transactions in the mempool. Helps monitor network connectivity and transaction dissemination efficiency.

### Mempool Recheck Count
- **Metric**: `cometbft_mempool_recheck_times`
- **Description**: Counts the number of times transactions are rechecked in the mempool. Provides insights into transaction re-evaluation processes, useful for analyzing mempool behavior.

### Mempool Size
- **Metric**: `cometbft_mempool_size`
- **Description**: Shows the number of uncommitted transactions in the mempool. Useful for understanding transaction backlog and network congestion.

### Mempool Size in Bytes
- **Metric**: `cometbft_mempool_size_bytes`
- **Description**: Indicates the total size of transactions in the mempool, in bytes. Helps assess memory usage and transaction volume awaiting processing.

### P2P Message Received Bytes
- **Metric**: `cometbft_p2p_message_receive_bytes_total`
- **Description**: Counts the number of bytes received for each P2P message type (e.g., blocksync_BlockResponse, consensus_BlockPart). Enables analysis of network traffic and data flow efficiency, helping to optimize P2P performance.

### P2P Message Sent Bytes
- **Metric**: `cometbft_p2p_message_send_bytes_total`
- **Description**: Shows the number of bytes sent for each P2P message type. Helps in assessing outbound traffic and understanding message distribution patterns.

### Number of Peers
- **Metric**: `cometbft_p2p_peers`
- **Description**: Displays the number of peers connected to the node. Important for understanding the node’s connectivity and resilience in the network.

### Block Processing Time
- **Metric**: `cometbft_state_block_processing_time`
- **Description**: This histogram metric measures the time taken between the BeginBlock and EndBlock events in milliseconds, with various time intervals. Helps monitor the block processing duration, which is essential for understanding the efficiency of block execution and identifying potential bottlenecks.

### Validator Set Updates
- **Metric**: `cometbft_state_validator_set_updates`
- **Description**: Indicates the total number of updates to the validator set. Tracks validator changes, allowing operators to monitor adjustments that impact consensus security.

### Consensus Parameter Updates
- **Metric**: `cometbft_state_consensus_param_updates`
- **Description**: Counts the total number of times consensus parameters have been updated since the process started. Useful for tracking changes in consensus configuration, which may affect network operation and performance.

### Go Garbage Collection Duration
- **Metric**: `go_gc_duration_seconds`
- **Description**: This summary metric captures the duration of garbage collection cycles in seconds, with various quantiles. Helps assess the impact of garbage collection on performance, allowing for memory management optimization.

### Goroutines Count
- **Metric**: `go_goroutines`
- **Description**: Shows the current number of goroutines. Useful for monitoring concurrency in Go applications, as excessive goroutines may indicate resource contention or potential memory leaks.

### Process CPU Seconds Total
- **Metric**: `process_cpu_seconds_total`
- **Description**: Total CPU time consumed by the process.

### Process Resident Memory Bytes
- **Metric**: `process_resident_memory_bytes`

