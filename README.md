Printing profiles of some Anycubic Water-Wash 2.0 for the Sisma Everes UNO DLP printer.

__THESE PROFILES ARE <ins>NOT</ins> VALID FOR Everes ZERO__

__ANYTHING YOU WILL FIND IN THIS PAGE IS COMPLETELY <ins>UNOFFICIAL</ins> AND IT'S JUST THE RESULT OF AN EMPIRICAL TRIAL AND ERROR PROCEDURE.__

# About the printer
Everes UNO's DLP projector is way more powerful (and hence faster) with respect to other resin printers. This means that any profile for any economic resin that one can find online will be completely unusable.

Moreover, Everes printers are built to print only at pre-fixed layer thichnesses (like $50\mu m$, $100\mu m$, ...) and so one must be able to calibrate every material keeping in mind that one must choose an allowed value for the layer thickness. For each material, both the $50\mu m$ and the $100\mu m$ are available.

Everes printers come with a SBP which has holes. this implies that you can't place object right on the surface of the build plate, but you have to place it floating and place it NOT parallel to the SBP. 

# Materials and profiles
In the [__/profile__](./profile) folder one can find the profiles for the following water-washable standard resins:
- [Gray_WW Anycubic](https://www.amazon.it/dp/B07VXPGVNH?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
- [Clear_WW Anycubic](https://www.amazon.it/dp/B07VXQ3C15?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
- [SmokyBlack_WW Anycubic](https://www.amazon.it/dp/B0F83W8KFT?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1).

If one wish to use a different material (or even a different color), one should start from a profile of a material which is as similar as possible to the new one, and adjust it properly acting on the following parameters:
- __bottom layer exposure time__: if the raft does not stick to the SBP, the time should be raised; if it sticks soo hard that the _auto-detach_ tool is not able to remove it, the time should be lowered.
- __exposure time__: if the supports are not strong enough, the time should be raised; if the supports are "overcooked" (namely if they're too much tick and coated with an "dirty" surface) or if you find a thin layer of partially polymerized resin on the bottom of the vat, the time should be lowered.
- __picture greyscale__: the exposure time for the supports will be intentionally set "too long" in order to make them more resistant. However, if the pixels curing the supports and those curing the part had the same brightness, the part would come out poorly, so a lower brightness is set for the pixels related to the part to be printed, while leaving the value 255 for the supports. This will be noticeable later, after the slicing, in the grayscale photographs.
- __light-off-delay__: this is the time between the moment the plate descends and the moment the next image is projected. This is to ensure the resin is completely still, otherwise partially solidified resin may settle where it should not. If the piece has a "dirty" surface, the time should be raised. If the piece has a very clean surface, one can try lowering it.

Main LLMs are quite capable of giving intelligent advice, but it must be specified that the printer is DLP, that it has a __tilting glass__ and that it has a VERY powerful projector, otherwise the answers will be based on "home" printers that have totally different profiles. You may also consider to give them these profile as starting point. 

However, one must consider that it will probably need some (i.e. tens) of tests to get a new profile. In particular, pay attention to these things:
- to avoid confusion, one may start with a big light-off-delay (i.e. $3:4s$) and reduce it only once all the other parameters has been tuned properly.
- the raft should be able to stick to the SBP but not too much.
- since one should not place object directly on the build plate, it's not meaningful to verify whether they stick too much or not.
- the light should cure just the current layer, and not the previous one. To check this one may print a cube (heigth $\simeq 20mm$ with a small horizontal hole (radius $\simeq 4mm$) and lower the exposure time and/or the picture greyscale.
- since the $100\mu m$ profile is harder to calibrate, you may first calibrate the $50\mu m$ one (easier), and then give it to an LLM to get an initial guess for the $100\mu m$ one.
- since the $100um$ is faster (one properly tuned) and because it's easier to highlight problems with the light-off-delay, you may prefer to tune this last parameter first with the $100\mu m$, and then use an initial guess from an LLM to adjust the $50\mu m$ one.

## Example pictures
In the [/pictures](./pictures) folder, one may find some example of pieces with some printing issues.

# Notes about the _tag holder_
As described in the printer manual, to use custom materials one havo to choose between using a _Custom_ cartridge, or using the _tag holder_.
- When choosing the first option, one must take into acount that in the profiles the field "Resin Name" has to be filled with "Custom".
- When choosing the second option, one must take into acount that in the profiles the field "Resin Name" has to be filled with "normal".
All the profiles are meant to be used with the _tag holder_. If it's not the case, one has to change the "Resin Name" accordingly.


