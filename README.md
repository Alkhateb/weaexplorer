# weaexplorer
Weacoin cryptocurrency, Scrypt/SHA-256, PoW/PoS supported blockchain explorer, forked from RPC Ace v. 0.8.0.
Easy install.
Copy all files to www directory on your web server (php 5.4/5.5 required) and write rpc login, pass and port in index.php
Done!
*****************

RPC Ace (and the extras) requires PHP version 5.4 or later, with CURL and JSON support enabled. Additionally, SQLite and zlib support is required to use the database storage feature.

Configurate `index.php` to your parameters:

    RPC_HOST = '127.0.0.1'              // Host/IP for the daemon
    RPC_PORT = 12345                    // RPC port for the daemon
    RPC_USER = 'username'               // 'rpcuser' from the coin's .conf
    RPC_PASS = 'password'               // 'rpcpassword' from the coin's .conf

    COIN_NAME = 'Somecoin'              // Coin name/title
    COIN_POS = false                    // Set to true for proof-of-stake coins

    RETURN_JSON = false                 // Set to true to return JSON instead of PHP arrays
    DATE_FORMAT = 'Y-M-d H:i:s'         // Date format for blocklist
    BLOCKS_PER_LIST = 12                // Number of blocks to collect for the blocklist

    DB_FILE = 'db/somecoin_db.sq3';     // Set to false to disable database storage

    // for the example explorer
    COIN_HOME = 'http://www.coin.org/'  // Coin website
    REFRESH_TIME = 180                  // Seconds between automatic HTML page refresh


For databaste storage it usually suffices to create a directory that is owned and writable by the user the httpd process runs under, and pointing the `DB_FILE` setting to a suitable filename inside that directory.

To get accurate transaction values your block chain must be reindexed (or built from scratch) with full transaction indexing, by setting `txindex=1` in the coin's .conf file.
