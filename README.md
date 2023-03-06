# Snapshot-Nolus 
Instructions

## Stop the service and reset the data
```
sudo apt update; sudo apt upgrade
```
## Download latest snapshot
```
curl -L https://snapshot.nolus.dosba.my.id/snapshot/nolus/nolus-snapshot-20230306.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.nolus
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
```
## Restart the service and check the log
```
sudo systemctl start nolusd && sudo journalctl -u nolusd -f --no-hostname -o cat
```
