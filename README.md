#!/bin/sh

echo "Installing Hamid Nador Skin..."

wget "https://raw.githubusercontent.com/hamidsat/hamid-skin/main/Hamid_Nador.zip" -O /tmp/skin.zip

if [ $? -ne 0 ]; then
    echo "Download failed!"
    exit 1
fi

unzip -o /tmp/skin.zip -d /

if [ $? -ne 0 ]; then
    echo "Unzip failed!"
    exit 1
fi

rm -f /tmp/skin.zip

echo "Restarting Enigma2..."
killall -9 enigma2

exit 0
