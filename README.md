# Python-Notes

pyenv problems with mac os 12.x
https://stackoverflow.com/questions/71577626/issues-installing-python-3-8-10-on-macos-12-3-monterey


CC=/usr/local/Cellar/gcc/11.3.0_2/bin/gcc-11 CFLAGS="-I$(brew --prefix openssl)/include -I$(brew --prefix bzip2)/include -I$(brew --prefix readline)/include -I$(xcrun --show-sdk-path)/usr/include" LDFLAGS="-L$(brew --prefix openssl)/lib -L$(brew --prefix readline)/lib -L$(brew --prefix zlib)/lib -L$(brew --prefix bzip2)/lib" pyenv install --patch 3.8.0 < <(curl -sSL https://github.com/python/cpython/commit/8ea6353.patch\?full_index\=1)
