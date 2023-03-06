---
title: FAQ / Troubleshooting
order: 11
---
# FAQ / Troubleshooting

Here resources will be gathered by responses to user issues and possible troubleshooting methods while working on Cradle. If you have any additional questions or issues, you can contact [Dr. Erik Enriquez](mailto:Erik.Enriquez01@utrgv.edu) for more information.

Additional resources will be added here periodically.

## ISSUE: Cannot connect to Cluster via ssh (Error port 22: Connection timed out)

1. The first thing that should be checked in this case is that you are currently online and able to visit other websites such as [the UTRGV homepage](https://www.utrgv.edu/).

If this is not the case, then the issue usually stems from a firewall issue or ssh configuration or setup.

2. Next, try using the [globalProtect VPN](https://support.utrgv.edu/TDClient/1849/Portal/KB/ArticleDet?ID=147386) to connect to the UTRGV network. This is necessary for connecting to the cluster when not on campus, but can also help in some cases even when accessing from campus.


3. If the issue persists, you may need to check that ssh (or [OpenSSH for Windows users](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui)) is setup and has [port 22 open](https://stackoverflow.com/questions/273159/how-do-i-determine-if-a-port-is-open-on-a-windows-server).