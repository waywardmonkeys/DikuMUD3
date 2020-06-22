# DikuMUD3
DikuMUD III using HTML and websockets. 

D-Day June 21, 2020

Get in touch if you'd like to contribute. There's a long to-do list. Everything from non-programming to HTML to C(++).

Documentation goes here:

https://wiki.dikumud.net/wiki/DikuMUD

Will get a copy sync'ed to GitHUB soon, many thanks to @ Damien Davison for help with that. 

How to build & launch

1) First build the binaries

       cd vme/src/
       make all # add -j8 to compile on 8 threads in parallel

2) Make sure `.def` files are pre-processed

       cd ../etc/
       make all

3) Then compile the zones:

       cd ../zone/
       ../bin/vmc -m -I../include/ *.zon

4) Now you're ready to launch, open four tabs in shell:

       cd ../bin/
       ./vme # tab1
       tail -f vme.log # tab2
       ./mplex -w -p 4280 # tab3
       tail -f mplex.log #tab4

You can also launch a telnet mplex using e.g. `mplex -p 4242`
And then `telnet localhost 4242`. But telnet is best for debugging

5) To open the client

       cd ../www/
       firefox index.html

Set the host to your fqdn or localhost and set the port to match mplex (4280 if you used that)
And you'll see the welcome screen in Firefox
