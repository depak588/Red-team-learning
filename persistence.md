# Persistence

In the previous chapter we have setup the reverse connection in the powershell-empire and in this chapter we will be using it for persistence so that after the victim restarted the machine we will again get the reverse connection.

First type agents to see the total agents running (green are the active one's and red are the dead ones).

<figure><img src=".gitbook/assets/1.png" alt=""><figcaption></figcaption></figure>

To interact with an agent type interact and hit tab to auto-complete the id, and in that type **info** to check the all details about the agent.

HIgh\_intergrity shows the previlege of the agent if it is false then it the agent is normal user and if it is true then it is High privilege user. In our case the user has normal privilege right now which we will be elevate in further steps.

<figure><img src=".gitbook/assets/2.png" alt=""><figcaption></figcaption></figure>

Now we will run a module privesc\_powerup\_allchecks because it runs all the checks included in the module to check that we can elevate our agent from that agent or not.

<figure><img src=".gitbook/assets/4.png" alt=""><figcaption></figcaption></figure>

You can check the output from the starkiller also go to agents > select the agent and in the tasks tab click on the task of which you want to see the output.

<figure><img src=".gitbook/assets/5.png" alt=""><figcaption></figcaption></figure>

After that we will use the module privesc\_bypassuac to get the elevated agent

<figure><img src=".gitbook/assets/6.png" alt=""><figcaption></figcaption></figure>

then set the listener to http and type execute. And in some time you will get the elevated agent showing in your starkiller and you can also see in terminal by typing agents.The agent which has the user logo is the elevated agent.

<figure><img src=".gitbook/assets/7.png" alt=""><figcaption></figcaption></figure>

Now from the normal agent we will run a module userland\_schtasks because "persistence/userland/schtasks" module is used to create a persistent backdoor on a compromised Windows system by adding a scheduled task that executes a PowerShell command. This module is used to maintain control of a system even after it has been restarted or the user has logged off.

<figure><img src=".gitbook/assets/9-1.png" alt=""><figcaption><p>Change the listener to http</p></figcaption></figure>

<figure><img src=".gitbook/assets/9-2.png" alt=""><figcaption><p>Change RegPath to "<strong>HKCU:\Software\Microsoft\Windows\CurrentVersion\Run"</strong></p></figcaption></figure>

<figure><img src=".gitbook/assets/9-3.png" alt=""><figcaption><p>Output </p></figcaption></figure>

After the schtask is successfully created you can also check that the new agent has high\_privilege by interacting it and type info to see it.

<figure><img src=".gitbook/assets/10.png" alt=""><figcaption><p>High_Integrity User.</p></figcaption></figure>