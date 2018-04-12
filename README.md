# Achilles-heel-of-Shell-scripting
Hi! Everyone~😉😉😉 I have just experienced a HORRIBLE `rm -rf` operation in my bash shell script!!!🙉🙉🙉

I was a little bit bad luck.😰😰😰

The code I wrote is:

    #!/bin/bash
    temp = "temp";
    rm -rf ./$temp;

I hope you will never try this way to delete things!!!😂😂😂

Beware of the spaces before and after the ` = ` (equal sign), when executing the script, you will get an alert in the terminal:

    $ -bash: temp: command not found

And then you will find EVERYTHING inside the current path are just GONE!!! GONE!!! GONE!!!😱😱😱

The cause is that the `"temp"` hasn't been assigned the `"temp"` as it supposes to be, there is even no `$temp` will be created/exist. And the script won't be stoped and will continue to execute `rm -rf ./$temp;` as `rm -rf ./` since the `$temp` is EMPTY!!!🙈🙈🙈

How fortunately I hadn't written it as `rm -rf /$temp;` otherwise you might guess what would happen!!!💀💀💀

So the correct way to achieve the attempted purpose should be:

    #!/bin/bash
    temp="temp"; # no space before and after the equal sign
    rm -rf $temp; # do not use the ./ or the dangerious / here

I think this is an Achilles' heel of Shell scripting~~~ 😝😝😝

Okay, wish you good luck in Shell scripting~~~ 😘😘😘
