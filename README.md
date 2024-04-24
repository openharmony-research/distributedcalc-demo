# Distributedcalc-demo

This is an app built using DevEco Studio.

## build and install
To download the code, run the following command:
```
git clone https://github.com/openharmony-research/distributedcalc-demo.git
```
Open the project in DevEco Studio. Then, build the hap. If you build successfully, you will see:
![build](images/2.png)

After a successful build, upload the `entry-default-signed.hap` to the server using command like `scp`.

Then start an OpenHarmony device using QEMU, connect to the device using the following command:
```
hdc tconn 192.168.137.2:5555
```

To install the app, use the following command:
```
hdc -t <ip> install xxx.hap
```

## Video

https://github.com/openharmony-research/distributedcalc-demo/assets/25260092/bb4192fb-a317-4d3f-ab00-4b197e0083b4


https://github.com/openharmony-research/distributedcalc-demo/assets/25260092/5be49ccb-93fa-41f3-b1c4-f316d59c28c5


https://github.com/openharmony-research/distributedcalc-demo/assets/25260092/0bff6024-d938-42fb-8520-100e7b5ace4e

## usage

To launch the demo app, use the command:
```
aa start -a MainAbility -b tutorial.samples.etsdistributedcalc
```

To experience the disrtibuted ability, you need to open 2 OpenHarmony device and pair them.

First you need 'touch' this button:

![button](images/7.png)

then choose the device

![device](images/8.png)

and the other device will requeset user's 'allow' to pair, after allowing
you need to type the pin code in the primary device

![pin1](images/9.png) ![pin2](images/10.png)

After pairing, type in the following command in QEMU to confirm permissions
```
uinput -T -c 350 740
```
and then
```
uinput -T -c 420 80
```
choose the device to connect
```
uinput -T -c 250 450
```
![connect](images/3.png)

then you can type any number in the calc, and you will see the two device display same content.
![content](images/4.png)
## exit
If you want to exit, you need to change the pair option to `local` to exit the app on the second device
```
uinput -T -c 420 80
```
```
uinput -T -c 250 400
```
then the app on the second device will exit.
Now you can type 
```
aa force-stop tutorial.samples.etsdistributedcalc
```
to exit the app on the primary device.
