Every 2.0s: lsof -i -P | grep dashboard                                                                                                                                      wai-mon-pc: Sat Sep  5 20:15:23 2026

dashboard 22723 wai-mon   7u  IPv6 119084      0t0  TCP *:8888 (LISTEN)
dashboard 22723 wai-mon   8u  IPv6  75440      0t0  TCP wai-mon-pc.lan:8888->wai-mon-pc.lan:43514 (ESTABLISHED)
dashboard 22723 wai-mon   9u  IPv6  75443      0t0  TCP localhost:8888->localhost:48166 (ESTABLISHED)
