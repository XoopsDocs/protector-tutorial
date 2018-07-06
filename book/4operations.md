# 4.0 Operating Instructions

** Rescue: Accidental self-banning**

If you somehow manage to ban yourself from your own site (most people seem to achieve this at least once :) go to XOOPS_TRUST_PATH/modules/protector/configs and delete the files in there. One of them contains the 'banned IP' data so getting rid of it (or better, editing it to remove your own IP) will restore your access to the site. Note that deleting it will also restore access of all other banned users, so editing it is a better idea if you aren't in a hurry.
