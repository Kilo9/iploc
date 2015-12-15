#!/bin/bash

args=$#
site=http://freegeoip.net

if [[ $args -lt 1 ]]; then
    echo "no ip provided"
    exit
fi

type=0

while getopts 'cxj' flag; do
    case "${flag}" in
        c) type = 0 ;;
        x) type = 1 ;;
        j) type = 2 ;;
    esac
done

if [[ $type -eq 0 ]]; then
    curl $site/csv/$1
elif [[ $type -eq 1 ]]; then
    curl $site/xml/$1
else 
    curl $site/json/$1
fi
