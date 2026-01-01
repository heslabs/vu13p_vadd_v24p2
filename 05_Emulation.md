# Launch Emulation


```
xauth nlist $DISPLAY | sed -e 's/^..../add /' | sudo xauth -f /root/.Xauthority source -
sudo -E ./run-E-CoreFlow.sh
```
