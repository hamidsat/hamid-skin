#!/bin/sh

wget "https://raw.githubusercontent.com/hamidsat/hamid-skin/main/hamid_nador.zip" -O /tmp/skin.zip

unzip -o /tmp/skin.zip -d /

killall -9 enigma2

exit 0
