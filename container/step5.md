# Running the new containerized software

Now the software has been installed and a new container image created.  It is
time to spawn a runtime of the container image and validate the software.  The
software we are using is a commandline command.  When you `run` the container,
it will be in interactive (`-it`) mode, based on the `moon-buggy` container
image, and the command run interactively will be `/usr/bin/moon-buggy`.

`podman run -it moon-buggy /usr/bin/moon-buggy`{{execute T1}}

<pre class="file">
<<< OUTPUT ABRIDGED >>>
               MM     MM   OOOOO    OOOOO   NN     N
               M M   M M  O     O  O     O  N N    N
               M  M M  M  O     O  O     O  N  N   N
               M   M   M  O     O  O     O  N   N  N
               M       M  O     O  O     O  N    N N
               M       M   OOOOO    OOOOO   N     NN

                     BBBBBB   U     U   GGGGG    GGGGG   Y     Y
                     B     B  U     U  G     G  G     G   Y   Y
                     BBBBBB   U     U  G        G          Y Y
                     B     B  U     U  G   GGG  G   GGG     Y
                     B     B  U     U  G     G  G     G    Y
                     BBBBBB    UUUUU    GGGGG    GGGGG   YY

<<< OUTPUT ABRIDGED >>>
</pre>

You can now play the Moon Buggy game, which is a text-based version of the
popular Moon Patrol.  When you are finished, use the `q` command to quit the
game, which will terminate the container.

Alternatively you can use `podman` to kill the running container from 
**Terminal 2**.

`podman kill $(podman ps | grep -v CONTAINER | cut -f1 -d" " )`{{execute T2}}

