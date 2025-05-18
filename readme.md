# TouchTone555 – NE555 Analogue Stylus Synth

The **TouchTone555** is a fully analogue, NE555-based synthesizer designed for learning about analogue electronics, and a bit of fun too. It was built from scratch as a personal deep-dive into oscillators, signal integrity, analogue filtering, and amplification.

Read the full project write up at: [www.darcyjprojects.xyz](https://www.darcyjprojects.xyz/index.php/2025/04/07/analogue-synth-project-touchtone555/)

[🔗 Share this project on LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=https://www.darcyjprojects.xyz/index.php/2025/04/07/analogue-synth-project-touchtone555/&title=TouchTone555%20Stylus%20Synth&summary=Check%20out%20this%20analogue%20NE555-based%20synthesizer%20project!)

![image](https://raw.githubusercontent.com/DarcyJProjects/touchtone555/main/media/1.png)

<p>
  This project is open source hardware under the <strong>CERN Open Hardware Licence Version 2 - Strongly Reciprocal (CERN-OHL-S v2)</strong>.
</p>
<img src="https://resources.oshwa.org/files/assets/oshw-logo-filled-color.png" alt="Open Source Hardware Logo" height="64" style="vertical-align: middle; margin-right: 8px;">

⚖️**Disclaimer:** This synthesizer was developed as a purely educational project to explore analogue electronics and sound synthesis. It is an independent work inspired by the vintage Stylophone, with no affiliation to Dubreq Ltd. or the original Stylophone product. All trademarks remain the property of their respective owners, and no copyright or trademark infringement is intended.

---

## 🎛 Features

- Based on the NE555 in astable multivibrator configuration as the main audio oscillator
- Individually tunable keys with trim potentiometers
- Touch interface for the keys with a stylus
- Octave switching via capacitor bank selection
- Vibrato modulation using an RC oscillator on the 555's CV pin
- Push-pull amplifier output with an LM386 buffer stage
- Onboard speaker with volume control, as well as a headphone output
- Custom designed PCB, with a descriptive silkscreen

<img title="" src="https://raw.githubusercontent.com/DarcyJProjects/touchtone555/main/media/3.png" alt="image" data-align="center">

---

## 📷 Demo

Check out the demo video here:<br>
👉 [Coming soon]<br>
🎵 Features a cover of Littleroot Town from Pokémon.

---

## 📜 License

This project is licensed under the **CERN-OHL-S v2 Strongly Reciprocal**.  

You are free to:

- **Study** and **modify** the design.

- **Make** and **sell** your own copies.

- **Distribute** modified versions — **as long as you:**
  
  - **Use the same CERN-OHL-S v2 license** (strong reciprocity), and
  
  - **Provide attribution to the original author**, and
  
  - **Include the original source files and any modifications**.

For full details, see the [LICENCE.txt](https://github.com/DarcyJProjects/touchtone555/blob/main/LICENCE.txt) file.

<img src="https://raw.githubusercontent.com/DarcyJProjects/touchtone555/main/media/5.png" title="" alt="image" width="271">

---

## ⚡How It Works

The TouchTone555 generates sound using an NE555 timer IC which is configured as an astable multivibrator. 

<img title="" src="https://raw.githubusercontent.com/DarcyJProjects/touchtone555/main/media/how_it_works/ne555-operation.png" alt="image" data-align="center" width="342">

Each key forms part of a series resistor network, which controls the oscillator’s frequency when the circuit is completed by touching a key with the stylus. The pitch is determined by which key is touched, and the selected octave capacitor.

<img title="" src="https://raw.githubusercontent.com/DarcyJProjects/touchtone555/main/media/how_it_works/resistor-network.png" alt="image" data-align="center" width="340">

Octave switching is achieved by toggling between banks of capacitors connected to the NE555. The more capacitance connected (capacitors in parallel), the lower the resulting octave.

<img title="" src="https://raw.githubusercontent.com/DarcyJProjects/touchtone555/main/media/how_it_works/octaves.jpg" alt="image" width="305" data-align="center">

Vibrato is achieved by modulating the NE555's control voltage pin using a separate RC oscillator, which uses RC (resistor-capacitor) pairs, capacitors, and a transistor to generate the low-frequency signal. The vibrato depth (or "mix") can be adjusted with the on-board trim potentiometer.

<img title="" src="https://raw.githubusercontent.com/DarcyJProjects/touchtone555/main/media/how_it_works/vibrato-depth.gif" alt="image" data-align="center" width="275">

The output signal is then passed through an LM386 and then through a simple push-pull amplifier to drive the onboard speaker and/or headphones. The LM386 acts as a buffer to ensure any loading from the amplifier doesn't affect the NE555 through its output pin. The supply voltage to the NE555 is also filtered with a resistor and capacitor to reduce any periodic voltage drop introduced by the amplifier.

<img title="" src="https://raw.githubusercontent.com/DarcyJProjects/touchtone555/main/media/how_it_works/amplifier.jpg" alt="image" width="318" data-align="center">

The power supply circuitry is simple: it supports a 9V DC input via either a JST connector, or a DC barrel jack. Two diodes prevent reverse polarity and ensure that the inputs cannot backfeed each other. 

<img title="" src="https://raw.githubusercontent.com/DarcyJProjects/touchtone555/main/media/how_it_works/psu.png" alt="image" data-align="center" width="275">

This project demonstrates the core concepts of oscillation, modulation, and amplification - no microcontroller required!

👉 For a full breakdown and more detail explanations, you can read the write-up here: [www.darcyjprojects.xyz](https://www.darcyjprojects.xyz/index.php/2025/04/07/analogue-synth-project-touchtone555/)

---

## 🛠️ Build Instructions

![image](https://raw.githubusercontent.com/DarcyJProjects/touchtone555/main/media/4.png)

### 🧾 What You’ll Need

- All components as outlined in the [BOM (Bill-of-Materials)](https://github.com/DarcyJProjects/touchtone555/blob/main/hardware/Bill%20of%20Materials.csv)
- To find the correct switches, speaker, audio jack, etc, see [Miscellaneous Parts](https://github.com/DarcyJProjects/touchtone555/blob/main/hardware/misc_parts.md)
- PCB (See [KiCad Project](https://github.com/DarcyJProjects/touchtone555/tree/main/hardware))
- Soldering iron and solder
- 9V Battery and connector or DC jack with 9V supply

⚠️ **Note:** I recommend selecting a **lead-free surface finish** (e.g., LeadFree HASL) when ordering the PCB as the stylus will put microscopic scratches in the exposed key pads during use. This could potentially produce harmful lead dust over time. Therefore, I highly recommend choosing lead-free!

### 🪛 Assembly

- Read each step fully before completing it to make sure you've read any handy tips :)
1. **Order the PCB**<br>
   The KiCad project files (and pre-exported gerber files) are located in [/hardware](https://github.com/DarcyJProjects/touchtone555/tree/main/hardware).

2. **Solder components in order**<br>
   Start with the smallest passive components (resistors, monolithic capacitors, diodes), then IC sockets, transistors, connectors/jacks/switches, ceramic and polyester capacitors, and finally the DC jack, trim potentiometers and the volume potentiometer.
   
   Soldering them systematically from smallest height to largest makes it a lot easier! Follow the component designators on the board, and in the BOM to make sure you are matching the correct values and components.
   
   Try your best not to get any solder on the exposed key pads, if you're nervous, you  can tape over them with some electrical or painters tape until you're finished soldering.
   
   For the polyester octave capacitors, try to get the values matched to each other as closely as possible as a small variance of 0.5 nF can throw off the pitch. This is less important for the lower octaves, but the highest octave with the single capacitor matters the most.
   
   For the vibrato monolithic capacitors, you can start with soldering the top three in, and adding the lower two if you want increase the vibrato frequency.

3. **Attach speaker & power**<br>
   The synth is designed to run on 9VDC, so I recommend using a 9V battery with a 9V battery to JST connector.

4. **Stylus**<br>

   In [/hardware](https://github.com/DarcyJProjects/touchtone555/tree/main/hardware), there is a 3D model of a stylus if you'd like to 3D print one, otherwise, a crocodile lead works really well too - just be careful not to push down too aggressively as to not damage the key pads.

   If you take the 3D model route, you can feed a thin gauge wire through the hole in the centre of the stylus, and solder a small piece of metal to the wire at the tip of the stylus. I used a mini spade connector which I soldered and then bent around the tip. I smoothed out the contact surface by creating a sphere of solder. You'll need to tape the tip to the stylus to ensure it doesn't come off. This stylus isn't perfect, but it works :)

5. **Tune keys**<br>
   Use a tuner app (with a chromatic mode) or oscilloscope to set the individual key pitches via the blue trim potentiometers.
   
   Set the octave to the lowest octave (lowest position on the octave switch) and then start tuning with the highest note on the keyboard, which corresponds to the right-most trim pot. Turning it clockwise will increase the pitch, and anticlockwise will decrease the pitch. You are aiming for the highest note (in the lowest octave) to be E6.
   
   Then work your way leftwards, one potentiometer at a time, reducing the pitch by one semitone each time.
   
   Remember, as this is a series resistor network, adjusting the pitch of one potentiometer will adjust the pitch of all the other keys to the left of that key. This is why you should work right to left.

6. **Vibrato depth**<br>
   By turning the vibrato depth trim pot, you can slightly adjust how strong the vibrato effect is. The change with each turn is minimal, so you'll need to turn it a lot to get any real difference. 

7. **Have fun!**

---

## 📂 Repo Structure

TouchTone555/<br>├── hardware/ # KiCad project + Gerbers + Stylus 3D model<br>├── media/ # Photos, demo videos, renders, etc<br>├── LICENCE # CERN-OHL-S v2<br>└── README.md # this file!<br>

---

### 💬 Feedback & Contributions

Feel free to fork, share, and build your own!<br>
If you build one, I’d love to see it - tag me on [LinkedIn](https://www.linkedin.com/in/darcywdjohnson/).

---

### 🔗 Acknowledgements

- This is an independent work inspired by the classic Stylophone with no affiliation to Dubreq Ltd. or the original Stylophone product. All trademarks remain the property of their respective owners, and no copyright or trademark infringement is intended.
- "Littleroot Town", composed by Gō Ichinose, from *Pokémon Ruby, Sapphire, & Emerald* (© Nintendo / Game Freak), is used under fair use as part of an educational demonstration.

---

## 🧠 Why I Built This

This was a personal challenge to push my understanding of analogue electronics beyond textbooks — especially in:

- Oscillator design
- Filtering
- Operational amplifiers
- Audio amplifiers
- Impedance buffering
- PCB design with custom exposed planes (the key pads)
- PCB footprint design

---

🛠️ Built for learning.<br>
❤️ Shared with the community.<br>
🔧 Darcy — [www.darcyjprojects.xyz](https://www.darcyjprojects.xyz)
