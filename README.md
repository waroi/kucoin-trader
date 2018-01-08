# Kucoin Trader (Beta)
@yasinkuyu - 2018

This is an experimental bot for auto trading the kucoin.com exchange.

## Configuration

1. Signup Kucoin ( Referral url: https://www.kucoin.com/#/?r=1w3Kd )
2. Enable Google 2-Step Authentication    
3. Go API Center, https://www.kucoin.com/#/user/setting/api
4. Create New Key
5. Rename config.sample.py to config.py
6. Get an Key and Secret, insert into config.py

        API key for account access
        api_key = ''
        Secret key for account access
        api_secret = ''

        API Docs: https://kucoinapidocs.docs.apiary.io/
7. Optional: run as an excutable application in Docker containers

## Requirements

    sudo easy_install -U requests
    or 
    sudo pip install requests
    
    Python 2.7
        import os
        import sys
        import time
        import config
        import argparse
        import threading
        import sqlite3

## Usage

    python trader.py --symbol KCS-BTC
    
    With option parameters

    python trader.py --symbol KCS-BTC --quantity 6 --profit 1.3 --loop 0 --orderid 0
    
    --quantity     Buy/Sell Quantity (default 6)
    --symbol       Market Symbol (default KCS-BTC)
    --profit       Target Profit (default 1.3)
    --orderid      Target Order Id (default 0)
    --wait_time    Wait Time (seconds) (default 1)
    --increasing   Buy Price Increasing  +(default 0.00000001)
    --decreasing   Sell Price Decreasing -(default 0.00000001)
    --prints       Scanning Profit Screen Print (default True)
    --loop         Loop (default 0 unlimited)

    Symbol structure;
        XXX-BTC  (Bitcoin)
        XXX-ETH  (Ethereum)
        XXX-NEO  (Neo)
        XXX-USDT (Tether)
        XXX-KCS  (KuCoin)

    All kucoin symbols are supported.
    
    Every coin can be different in --profit and --quantity.
    Min amount each order 1.0
    
    Variations;
        trader.py --symbol NEO-KCS --quantity 100 --profit 3
        trader.py --symbol KCS-BTC --quantity 6 --profit 1.1
        trader.py --symbol ETH-USDT --quantity 0.3 --profit 1.5
        ...
    
## Run in a Docker container

    docker build -t trader .

    docker run trader
 
## DISCLAIMER

    I am not responsible for anything done with this bot. 
    You use it at your own risk. 
    There are no warranties or guarantees expressed or implied. 
    You assume all responsibility and liability.
     
## Contributing

    Fork this Repo
    Commit your changes (git commit -m 'Add some feature')
    Push to the changes (git push)
    Create a new Pull Request
    
    Thanks all for your contributions...
    
## Failure


## Roadmap

    - January 15, 2018 Beta
     
## License

    Code released under the MIT License.

#### Tip Box

[Wallets](http://yasinkuyu.net/wallet) 

---