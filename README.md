#!/bin/sh

echo "Installing Hamid Nador Skin..."

rm -f /tmp/skin.zip
rm -rf /tmp/Hamid_Nador

wget "https://raw.githubusercontent.com/hamidsat/hamid-skin/main/Hamid_Nador.zip" -O /tmp/skin.zip

if [ $? -ne 0 ]; then
    echo "Download failed!"
    exit 1
fi

unzip -o /tmp/skin.zip -d /tmp/

if [ $? -ne 0 ]; then
    echo "Unzip failed!"
    exit 1
fi

mkdir -p /usr/share/enigma2/MetrixHD/skinparts/

cp -r /tmp/Hamid_Nador /usr/share/enigma2/MetrixHD/skinparts/

rm -rf /tmp/Hamid_Nador
rm -f /tmp/skin.zip

echo "Restarting Enigma2..."

killall -9 enigma2

exit 0
