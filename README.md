# Amigacoin Integration/Staging Tree
http://www.amigacoin.org/

Support Amiga community, please!

## What is Amigacoin?
Amigacoin is a clone of Dogecoin (another open source peer-to-peer Litecoin-derived cryptocurrency).

 - 2 minute block targets
 - 2 billion total coins
 - 100 to 1000 random coins per block
 - 1440 blocks to retarget difficulty

## License
Amigacoin is released under the terms of the MIT license. See [COPYING](COPYING)
for more information or see http://opensource.org/licenses/MIT.

## Development and contributions
Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

### Building amigacoind on Linux (Ubuntu/Debian)
sudo apt-get install build-essential libssl-dev libdb5.1++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev
cd src/
make -f makefile.unix USE_UPNP=1 USE_IPV6=1 USE_QRCODE=1

### Ports
RPC 22111
P2P 22112
