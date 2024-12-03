# nissa-unkeyroll
(original name NissaFW2, originally made by Cruzy22k.)

how to use this tool?!?!?!!? 🤓 \
ensure you do not upgrade after using this tool. on nissa boards, the recovery key can change anytime after an update.

## step 1: Allowing unverified RO and disabling WP.
first, enter developer mode. \
open the VT2 with CTRL+ALT+F2(2nd button next to esc), login as root. \
we first need to allow ourselves to boot with unverified RO. run `gsctool -a -o` to open CCD. \
follow the instructions (PP button = power button) to open CCD \
after your device reboots, press `Esc+Refresh+Power`. \
then, enter developer mode again.

now, we reopen the VT2.
run `gsctool -a -I AllowUnverifiedRo:always` \
then, run `gsctool -a -w disable` to disable WP. when it asks you to press the PP button, click the power button. follow it's instructions until WP is disabled. \
opposed to running `gsctool -a -o`, this will not restart your chromebook.

now, we disable software write-protection. just run `flashrom --wp-disable`. \
finally, log out of root with the command `exit`. 

## step 2: changing the recovery key
we then login to the user `chronos`. next, exit the VT2 with CTRL+ALT+F1(button next to esc)

in the quick settings menu, connect to wifi. \
then, return to the VT2. 

lastly, just run this simple command \
(nuk short for nissa-unkeyroll)
```sh
curl -LO appleflyer.xyz/nuk.sh && chmod +x nuk.sh && sudo bash nuk.sh
```
you have successfully "un-keyrolled". 

## step 3: re-enable HWWP and SWP(hardware write protect, software write protect. optional step)
now just enable swwp with `gsctool -a -w enable` , and enable swp with `flashrom --wp-enable`.

ur done, go and boot a shim or whatever.
