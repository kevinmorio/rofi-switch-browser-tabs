#!/usr/bin/env bash

TABS_JSON=$(chrome-remote-interface list | sed -e "s/^'//" -e "s/'$//" | jq -r 'map(select(.type == "page") | {id: .id, title: .title})')

if [[ -z $@ ]]; then
    TAB_NAMES=$(echo "$TABS_JSON" | jq -r 'map(.title) | .[]')

    echo "$TAB_NAMES"
else
    TAB=$*

    TAB_ID=$(echo "$TABS_JSON" | jq -r "map(select(.title | contains (\"${TAB//\"/\\\"}\")) | .id) | .[]")

    chrome-remote-interface activate "$TAB_ID" >/dev/null
fi
