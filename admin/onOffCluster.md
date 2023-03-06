---
title: Power On/Off
order: 3
---
# Power On / Off Procedures

## Power Off

Whenever needed, such as during a scheduled shutdown, The following steps can be taken to gracefully and safely shut down the cluster:

1. Unmount wekaFS: 
   ```
   umount /weka/scratch
   ```
2. Stop IO services to wekaFS: 
   ```
   weka cluster stop-io
   ```
   * (may be completed through GUI as well)
3. Shutdown GPU nodes: 
   ```
   fornodes -b gpu -i 1-8 “shutdown -h now”
   ```
4. Same for SXM nodes:
   ```
   fornodes -b sxm -i 1-4 “shutdown -h now”
   ```

5. Shutdown Login and backup nodes: 
    ```
   fornodes -b stor001 “shutdown -h now”
    ```
6. Same for login001 node: 
   ```
   fornodes -b login001 “shutdown -h now"
   ```

7. Shutdown weka nodes:
   ```
   fornodes -b weka -i 1-6 “shutdown -h now”
   ```

8. Power down head node

## Power On Sequence

To Power on, we can use the following:

1. Power on head node (riogrande)
2. Power on Weka nodes
   ```
   ipmipower -u ADMIN2 -p UTRGV@6002900 -h weka0[1-6]-ipmi --on
   ```
3. Check that Weka nodes to start up. We can check the status and should see all nodes as `UP` with the following command:
   ```
   weka cluster host
   ```
4. Start Weka FS
   ```
   weka cluster start-io
   ```
5. Start Login and Backup nodes (login001, stor001)
   ```
   ipmipower -u ADMIN2 -p UTRGV@6002900 -h login001-ipmi --on

   ipmipower -u ADMIN2 -p UTRGV@6002900 -h stor001-ipmi --on
   ```
6. Start compute nodes
   ```
    ipmipower -u ADMIN2 -p UTRGV@6002900 -h gpu00[1-8]-ipmi --on

    ipmipower -u ADMIN2 -p UTRGV@6002900 -h sxm00[1-4]-ipmi --on
   ```