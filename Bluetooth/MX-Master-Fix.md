# Fix Logitech MX Master pairing problem
MX Master can pair in GUI but not function at all. Following steps can solve this problem.
Enter the command:
```
sudo bluetoothctl
[bluetooth]# power off
[bluetooth]# power on
[bluetooth]# scan on
```
Assume XX:XX:XX:XX:XX:XX is MX Master's MAC address. You can figure it out if it is detected after issuing command `scan on`.

Once you find that, continue inputing like below:
```
[bluetooth]# connect XX:XX:XX:XX:XX:XX
[MX Master]# trust
[MX Master]# connect XX:XX:XX:XX:XX:XX
[MX Master]# pair
[MX Master]# unblock
[MX Master]# power off
[bluetooth]# power on
```
MX master must work normally.

Credit to [this post](https://askubuntu.com/a/769095).
