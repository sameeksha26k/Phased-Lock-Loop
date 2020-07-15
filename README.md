# Introduction
> This project is implementation of Phased lock loop using open sourceware and cmos 180nm technology.

## Phased Lock Loop
> This PLL comprises of a phase detector, Charge Pump, Loop filter, and a voltage-controlled oscillator(VCO) which is current starved.The phase detector or comparator compares the input frequency with feedback frequency. The output of the phase detector is proportional to the phase difference between input and output frequency. The VCO is a sinusoidal generator whose frequency is determined by a voltage applied to it from an external source. In effect, any frequency modulator may serve as a VCO. PLL has quite many applications in this electronics domain which includes Frequency Synthesizer in mobile phones or Clock generation in microprocessors.

### Sourceware
> The design is implemented using one of the open sourceware -`LTSpice`.

### Installation
> Steps for installation of the simulator in LINUX:
1) As it isn't directly supported, we need to download WineHQ.
2) Copy paste the commands one after another in the terminal for downloading & installing:
```
sudo dpkg --add-architecture i386
wget -O - https://dl.winehq.org/wine-builds/winehq.key | sudo apt-key add -
sudo add-apt-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ focal main'
sudo apt update
sudo apt install --install-recommends winehq-stable
```
3) Download [LTSpice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html).
4) Click on `Download for Windows`.
5) Install as directed on the screen by clicking on `->next`.
6) After installing click on open with `WineHQ windows program loader`.
![Screenshot from 2020-06-16 17-13-27](https://user-images.githubusercontent.com/34000135/84770617-81568200-aff5-11ea-87b7-fab9d7952eff.png)

> Steps for installation of the simulator in WINDOWS/MAC:
1) Download [LTSpice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html).
2) Install as directed on the screen by clicking on `->next`.

### Implementation
Steps to implement the project:
1) Click on the desktop icon, `LTSpice VII`.
2) Click on `New Schematic` and build your circuit diagram by placing components. 
3) Click on the `Simulate` button for waveforms generation.
4) For further help with LTSpice refer the manual [LTSpice guide](http://dept.me.umn.edu/labs/hmd/lab/docs/LTspice_Guide.pdf)

### Library
> To use the 180nm CMOS technology
1) Download this [CMOS@180nm_NMOS]()
    & [CMOS@180nm_PMOS]()
2) Copy the code excluding .end until the brackets for both nmos & pmos.
![Screenshot from 2020-06-19 00-50-59](https://user-images.githubusercontent.com/34000135/85063256-7f441d00-b1c7-11ea-90a2-50c1f0e943c7.png)

3) Click on .opt in LTSpice and paste the code there.
![Screenshot from 2020-06-16 16-36-15](https://user-images.githubusercontent.com/34000135/84770820-e5794600-aff5-11ea-9dd2-5175b68d8fe5.png)


### Accessing my files
1) Click on `Download zip file`.
2) Click on`.asc` file which will open the schematic.
3) Click on simulate to check the waveforms.
4) To view the `Spice Netlist`. Go to `Tools ->Export Netlist'.
![Screenshot from 2020-06-19 00-51-49](https://user-images.githubusercontent.com/34000135/85063318-984cce00-b1c7-11ea-9a5a-9042b3f1419b.png)

![Screenshot from 2020-06-19 00-52-05](https://user-images.githubusercontent.com/34000135/85063377-aef32500-b1c7-11ea-9e4d-9e0eabb4c93f.png)

NOTE: The netlist exported in this will be .cir file. So to make it universally accessible, we need to run it in `ngspice`.

### Simulations in NGSpice
> Windows
1) Download [ngspice](https://sourceforge.net/projects/ngspice/files/) and then [ngspice gui](http://ngspice.sourceforge.net/download.html).
2) Unzip the folder, then 'DuSpiceStart.exe' & 'DuSpicePlot.exe' will appear.
3) Click on 'DuSpiceStart.exe -> New file -> include .cir file'.
4) Click on 'Setup -> include ltspice '.
![WhatsApp Image 2020-06-19 at 17 58 12](https://user-images.githubusercontent.com/34000135/85132651-d6450300-b256-11ea-8ae9-481432289f2c.jpeg)

5) Click on `Start interact`, ltspice will open.
6) Trace the plot and the waveform will be generated.
![Screenshot (388)](https://user-images.githubusercontent.com/34000135/85229331-ad637000-b406-11ea-8e7d-d00147a0f727.png)


> Windows(directly by ngspice command prompt)
1) After unzipping, Spice64 folder will be created.
![Screenshot (400)](https://user-images.githubusercontent.com/34000135/85324144-ed9a1f80-b4e6-11ea-9622-d1358de2a0d0.png)
2) Click on `Spice64 -> bin .
3) Here `ngspice.exe' & 'ngspice_con.exe' will be present.
4) First export all your files(eg: on-chip PLL.asc, .log, .raw, spice.cir)
![Screenshot (401)](https://user-images.githubusercontent.com/34000135/85324250-1de1be00-b4e7-11ea-9d45-1e0efd1322b7.png)
5) Click on `ngspice.exe'
6) enter your .cir file
![Screenshot (392)](https://user-images.githubusercontent.com/34000135/85324280-2cc87080-b4e7-11ea-87e7-7ea2d22942fc.png)
7) Enter `run`
![Screenshot (393)](https://user-images.githubusercontent.com/34000135/85324309-3b168c80-b4e7-11ea-9b8d-f99e8c0115e4.png)

8) Enter `display`
![Screenshot (395)](https://user-images.githubusercontent.com/34000135/85324921-53d37200-b4e8-11ea-90d7-ebf32b767f75.png)

9) Now enter plot respective values.
![Screenshot (397)](https://user-images.githubusercontent.com/34000135/85324915-52a24500-b4e8-11ea-9d2c-ba2e47b20dc4.png)

![Screenshot (398)](https://user-images.githubusercontent.com/34000135/85324914-5209ae80-b4e8-11ea-904c-c3ccb9eb96e5.png)

![Screenshot (399)](https://user-images.githubusercontent.com/34000135/85324908-4fa75480-b4e8-11ea-9283-c8f80818ccc1.png)


>Linux
1) To install type `sudo apt-get install -y ngspice`.
2) After installation, to enter into the shell type `ngspice`.
3) To simulate type `source filename.cir`.

![Screenshot from 2020-06-19 18-06-30](https://user-images.githubusercontent.com/34000135/85134303-e6aaad00-b259-11ea-9b8d-a711d070cb3b.png)
    Here I've first changed the directory to the location where `.cir` file is present. command is
    cd 'location'.


### Schematic

- Phase detector
![PFD](https://user-images.githubusercontent.com/34000135/85063542-ebbf1c00-b1c7-11ea-96c4-bf2fa5431680.png)

- Charge Pump & Low Pass Filter
![ChargePump LPF](https://user-images.githubusercontent.com/34000135/85063505-e06bf080-b1c7-11ea-81b1-f32a3a00f615.png)

- Voltage Controlled Ring Oscillator
![VCO](https://user-images.githubusercontent.com/34000135/85063460-cc27f380-b1c7-11ea-91c1-be1fcb28066e.png)


### WAVEFORMS

![Screenshot from 2020-06-19 19-30-15](https://user-images.githubusercontent.com/34000135/85141124-e7e0d780-b263-11ea-93b0-2dfb4d223e4e.png)

> In this the output is of V(Clk_1) & V(Clk_2).

![Screenshot from 2020-06-19 19-29-46](https://user-images.githubusercontent.com/34000135/85141048-cc75cc80-b263-11ea-9c85-44ad0849b35e.png)

> This is V(up) & V(down)

![Vcont](https://user-images.githubusercontent.com/34000135/84765449-dcd04200-afec-11ea-8383-7b36e1fc71f2.png)

> This is V(cont) which comes out of charge pump & LPF.







Contact Information
--------

-  SAMEEKSHA KONAKALLA- B.Tech Electronics and Communication Engineering, SRM University AP <26sameekshak@gmail.com>
