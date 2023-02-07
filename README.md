# **Solder Reflow Plate**

###### By AfterEarth Ltd

This is a largely unmodified version of the design by AfterEarthLTD that was also seen on a [GreatScott! video](https://github.com/DerSpatz/PCB-reflow-solder-heat-plate). I have made some tweaks to the software to get it to work on the ATMega4809 and also added instructions on how to build it and program it. It does work, but there are some problems with the design. I am working on newer designs but the best design out there today is probably the one by [DerSpatz](https://github.com/DerSpatz/PCB-reflow-solder-heat-plate)

## WARNING!!!

This design lacks safety features to limit the amount of power it may draw or the temperature it may reach and there are other issues with the electrical design. With a suitable power supply and as long as the software doesn't have any major bugs, it can be operated without issue but there is a real risk that it could start a fire in the event of a software bug or other fault. Do not leave it unsupervised while connected to power. If you're designing your own version, some considerations you may want to include are:

- Safety!!! What can happen with your design in the event of a hardware or software fault? Can it draw enough power to catch fire? At a minimum, some kind of overcurrent protection like a fuse would be prudent.
- Heating element resistance. The original board layouts have very low resistance that typically ends up around 0.9 ohms or so. A higher resistance that's closer to your design maximum power at 100% duty cycle would help ensure that the device cannot draw excessive currents, overheat and catch fire in the event of a fault. Since the design goal was about 60W, something closer to 2 ohms at peak temperatures would be more prudent to help prevent large overcurrent faults. For about 2.1 ohms at 180 celsius, you'd want about 1.3 ohms at 20 celsius.
- Input capacitance and PWM frequency. The original design left the PWM frequency at the default value of 490Hz. That, coupled with the relatively low input capacitance of 100uF meant that at all but the lowest duty cycles, the input capacitance was discharged and the supply exposed to the full load of the heating element. This is not an issue if you're working with a 20A supply, but if you're working on the assumption that 5A is enough, you're likely overloading your power supply. Firmware should be written to use much higher PWM frequency in conjunction with much larger input capacitance to ensure effective buffering between the supply and the heating element load.
- Thermal gradients. The standard layout has a uniform track layout across the entire board, but since you lose heat much more easily at the edge than in the centre, thermal gradients of 50 celsius between the centre of the board and the edge are not uncommon. Having thinner tracks near the edge can help reduce this effect.
- Thermal sensing. The temperature sensor off the side of the hotplate is ineffective at accurately sensing hotplate temperature and will likely be 20-30 celsius lower than the temperature at the edge of the board, even if you install it as close to the board as possible. Ideally, the sensor setup should measure temperature within the hotplate area itself or on the board being reflowed. Suggested approaches are using the heating element itself as the sensor, using a remote sensor that can be attached to the board being reflowed or possibly using some kind of thermography or IR sensor.

## UPDATE!!!

Join the [DISCORD!](https://discord.gg/YzhG6FcCRA)

Checkout the new Ver 3.0 design. Very similar to Ver 2.4 but now comes with ATmega4809 as its availability is much better than the 328p at the moment. Code is still in development but the board designs are available in the Board Versions Folder.

## Versions

- 70mm x 50mm (Ver 2.4)
  - 12VDC (5A Minimum)
  - 5.5mm x 2.5mm Barrel Jack
  - 0.91" OLED Display
  - ATmega328p Microprocessor

- 70mm x 50mm (Ver 3.0) **NEW**
  - 12VDC (5A Minimum)
  - 5.5mm x 2.5mm Barrel Jack
  - 0.91" OLED Display
  - ATmega4809 Microprocessor

## About the Project

Like any good nerd does I've been expanding my hobby horizons.
I've gone from breadboard, to perf board, through-hole, to SMD, ever increasing circuit complexity and improving my knowledge.
But I've become frustrated with the difficulty of SMD soldering.
Regular soldering jogs small components and needs lots of flux.
Hot air damages plastics.
Hot plates are expensive and can be big wastes of space.

*"But you're a nerd"* I hear you cry, *"why don't you DIY a solution?"*.

[Electronoobs](https://www.youtube.com/channel/UCjiVhIvGmRZixSzupD0sS9Q) shows a great DIY solution using an old clothes iron hot plate.
You can watch his video [here.](https://www.youtube.com/watch?v=C7blZigaaaA)
Have a go!

While I love this solution, I wanted to develop something smaller and more permanent.
Hence the Solder Reflow Plate was born, a PCB-based, MOSFET controlled heater, perfect for easily reflowing SMD components giving surprisingly professional results. Furthermore, these results are achieved without breaking the bank or taking up an enormous amount of desk space.

And so, this nerd bestows upon the world his project, fully open-source and hackable.
Here's hoping that it may be used to develop skills, build custom circuit boards, and make quality designs possible to all!

## Purchase

- Register your email address at [www.solderreflowplate.co.uk](https://www.solderreflowplate.co.uk) to know when it is available to buy!
- There is a worldwide shortage of ATmega328p Microcontrollers. I'm currently working on a small redesign for a more readily available chip.
- Purchase will be available soon!

## License

All parts of this project are covered by a [MIT license](LICENSE).
That means it is entirely open-source, so you get access to everything! (just without warranty or liability)
Feel free to download, customise, hack, and commercialise to your nerdy heart's content.

Want the **easy** life?!
**Purchase** the default design above!
Its fully functional, cheaper than customising, and helps to feed the creator's caffeine addiction 🙃
