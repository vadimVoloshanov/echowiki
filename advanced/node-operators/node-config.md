# Node Config

The node supports two configuration options:

- using the configuration file
- using start arguments

The configuration file is located at $DATADIR as config.ini. The config file will be created automatically when the node starts, if it was not there before. In the file you can find explanations for each parameter.

Use `./echo_node --help` to show all available arguments.

```bash
$ ./echo_node --help
Echo Node:
  -h [ --help ]                         Print this help message and exit.
  -d [ --data-dir ] arg                 Directory containing databases,
                                        configuration file, etc.
  --sidechain                           Enable sidechain plugin
  --testnet                             Use testnet options preset
  --devnet                              Use devnet options preset
  -v [ --version ]                      Print version information
  --configure-keys                      Encrypt private keys in interactive
                                        mode and save it to keys.file

  --create-genesis-json                 Create a genesis.json at corresponding
                                        datadir. Depending on which options
                                        preset is selected (mainnet or testnet)
                                        it will output different Genesis State.
  --example-genesis-json arg            Path to create an example Genesis State
                                        at. If a well-formed JSON file exists
                                        at the path, it will be parsed and any
                                        missing fields in a Genesis State will
                                        be added, and any unknown fields will
                                        be removed. If no file or an invalid
                                        file is found, it will be replaced with
                                        an example Genesis State.
  --replay-blockchain                   Rebuild object graph by replaying all
                                        blocks
  --resync-blockchain                   Delete all blocks and re-sync with
                                        network from scratch
  --force-validate                      Force validation of all transactions
  --genesis-timestamp arg               Replace timestamp from genesis.json
                                        with current time plus this many
                                        seconds (experts only!)

  --p2p-endpoint [=arg(=127.0.0.1:13375)]
                                        Endpoint for P2P node to listen on
  -s [ --seed-node ] arg                P2P nodes to connect to on startup (may
                                        specify multiple times)
  --seed-nodes arg                      JSON array of P2P nodes to connect to
                                        on startup
  -c [ --checkpoint ] arg               Pairs of [BLOCK_NUM,BLOCK_ID] that
                                        should be enforced as checkpoints.
  --rpc-endpoint [=arg(=127.0.0.1:8090)]
                                        Endpoint for websocket RPC to listen on
  --rpc-tls-endpoint [=arg(=127.0.0.1:8089)]
                                        Endpoint for TLS websocket RPC to
                                        listen on
  -p [ --server-pem ] [=arg(=server.pem)]
                                        The TLS certificate file for this
                                        server
  -P [ --server-pem-password ] arg      Password for this certificate
  --genesis-json arg                    File to read Genesis State from
  --api-access arg                      JSON file specifying API permissions
  --plugins arg (=account_history,echorand)
                                        Comma-separated list of plugins which
                                        will be activated in addition to
                                        default.Example: --plugins="sidechain,r
                                        egistration,shapshot"


Options for plugin echorand:
  --start-echorand                      Enable Echorand, even if the chain is
                                        stale.
  --account-info arg                    Pairs of [AccountID, WIF private key]
                                        (may specify multiple times)

Options for plugin sidechain:
  --sidechain-eth-committeeman arg      Sidechain: Pair of [account_id,
                                        eth_private_key] that should correspond
                                        to committee account (may be specified
                                        multiple times)
  --eth-rpc-ip [=arg(=127.0.0.1)]       Sidechain: RPC address of Ethereum node
  --eth-rpc-port [=arg(=18332)]         Sidechain: RPC port of Ethereum node
  --sidechain-eth-disable               Sidechain: Disable Ethereum service
  --sidechain-btc-testnet               Sidechain: Run btc sidechain for
                                        Bitcoin testnet
  --sidechain-btc-committeeman arg      Sidechain: Tuple of [account_id, WIF
                                        BTC private key] (may specify multiple
                                        times)
  --btc-rpc-ip [=arg(=127.0.0.1)]       Sidechain: RPC address of Bitcoin node
  --btc-rpc-port [=arg(=18332)]         Sidechain: RPC port of Bitcoin node
  --btc-rpc-user arg                    Sidechain: Bitcoin RPC user
  --btc-rpc-password arg                Sidechain: Bitcoin RPC password
  --sidechain-btc-disable               Sidechain: Disable Bitcoin service

Options for plugin registration:
  --registrar-account arg               Registration: ID of registrar account
                                        on this node (should be imported as
                                        account-info)
  --registration-difficulty arg (=)    Registration: complexity of POW task to
                                        register account

Options for plugin account_history:
  --track-account arg                   Account history: Account ID to track
                                        history for (may specify multiple
                                        times)
  --partial-operations arg              Account history: Keep only those
                                        operations in memory that are related
                                        to account history tracking
  --max-ops-per-account arg             Account history: Maximum number of
                                        operations per account will be kept in
                                        memory

Options for plugin snapshot:
  --snapshot-at-block arg               Snapshots: Block number after which to
                                        do a snapshot
  --snapshot-at-time arg                Snapshots: Block time (ISO format)
                                        after which to do a snapshot
  --snapshot-to arg                     Snapshots: Pathname of JSON file where
                                        to store the snapshot

```
