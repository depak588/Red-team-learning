---
description: (HIDING PROCESS)
---

# Linux Defense Evasion (Method #1)

First get a reverse connection from the victim machine, and then clone this file in the temp file of the victim machine.

{% embed url="https://github.com/gianlucaborello/libprocesshider" %}

<figure><img src=".gitbook/assets/1 (2).png" alt=""><figcaption></figcaption></figure>

Now check the running process in the victim machine by typing **ps -aux** you can see the admin can clearly identify the process.

<figure><img src=".gitbook/assets/3 (2).png" alt=""><figcaption></figcaption></figure>

Now in the process hider dir. open the **processhider.c** file and change the process to file **evil\_script.py** to your payload.

<figure><img src=".gitbook/assets/4(1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/5 (2).png" alt=""><figcaption></figcaption></figure>

After saving it type **make** to create the process and ls to check whether it is created or not.

<figure><img src=".gitbook/assets/6 (2).png" alt=""><figcaption></figcaption></figure>

Now again run a nc server and execute the same payload&#x20;

<figure><img src=".gitbook/assets/7 (2).png" alt=""><figcaption></figcaption></figure>

and when you get the reverse connection check again the processes and you will not find your payload process.

<figure><img src=".gitbook/assets/8 (2).png" alt=""><figcaption></figcaption></figure>
