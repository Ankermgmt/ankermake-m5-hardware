# Hotend Fan

![](https://user-images.githubusercontent.com/242382/227745308-f34a1ea8-7dc7-4f1d-949e-ccab0c5ac17a.png)

Manufacture: `Guangdong Dongguan Electric Motor Co`  
Model: `bb04015y4`  
Voltage: `24v`  
Wires: `4*`  
Connector: `JST-PH`
Outer Size: `40x40x15mm`
Mounting Hole Distance: `32x32mm`


1. The fan is a 4 wire fan, with 1 wire missing
2. The yellow wire is actually a PWM wire, not a Tachometer wire (completely proprietary and not standard)
3. Fan can run on both a 490hz PWM signal (arduino analog pin default) and a standard 25khz PWM signal. 
4. Fan does NOT have low RPM protection circuitry built in. (Meaning its possible to turn the fan _off_ with PWM.)
5. PWM is non-inverted meaning 0% duty cycle = off, 100% duty cycle = max rpm


Most 4 wire DC fans use a yellow wire as a tachometer and a blue or green for PWM control. For whatever reason Anker chose to use a manufacture who decided to omit the blue/green wire and use the yellow wire instead. 

This means you likely cannot buy a drop in replacement fan. It may be possible to modfiy any standard 4 wire fan by removing the 4th pin and moving pin 4 (blue/green) to pin 3 (yellow). 


It is suspected that you could solder a wire to the open pad number 3 and get techometer readings. 


![](https://user-images.githubusercontent.com/242382/227745812-547f4ba0-86cc-48eb-a090-1afa482aebb5.png) Photo Credit Cisien


### Size

The fan is likley a custom made fan for Anker. The fan is 40x40x15mm and has mounting holes 32x32mm apart. These dimensions are not typical.

## PWM Control

Here is sample arduino code that can be used to control the fan

https://gist.github.com/spuder/06122b59148af579ae1f1ea644ac7595

![](https://user-images.githubusercontent.com/242382/227745246-be13c852-2589-4b57-bca2-d9821cebf20c.png)