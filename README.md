# BachelorThesis
Material created during the creation of the bachelor's thesis, concerning the performance analysis and expressiveness of Intrusion Detection System rules generated in LUA language for industrial scenarios.

## How to use the project
1. Enter `Infrastructure` folder and run `vagrant up`. Then start client and server with `vagrant ssh client` and  `vagrant ssh server`.
2. In `server` install Python and pyModbus.
3. In `client` install Python, Suricata and pyModbus.
   - Place `suricata.yaml` into `/etc/suricata/`
   - Place `modbus_detect.rules` into `/etc/suricata/rules/`
   - Place `prova1.lua` into `/etc/suricata/rules/`
   - Place `ceftest.lua` and `script1.lua` into `/etc/suricata/lua-outputs`
4. Put into `Infrastructure` folder:
   - `client_async.py`
   - `client_payloads.py`
   - `helper.py`
   - `server_async.py`
   - `server_payloads.py`
5. Run server with `python3 server_payloads.py -c tcp -p 502`
6. Run client with `python3 client_payloads.py -c tcp -p 502 --host 192.168.1.61`
7. Check the two new-created log files `ceftest.cef` and `luatest.log` for alerts.
