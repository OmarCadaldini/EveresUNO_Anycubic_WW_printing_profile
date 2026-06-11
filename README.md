Printing profiles of some Anycubic Water-Wash 2.0 resins for the Sisma Everes UNO DLP printer.

**THESE PROFILES ARE <ins>NOT</ins> VALID FOR Everes ZERO**

**ANYTHING YOU FIND ON THIS PAGE IS COMPLETELY <ins>UNOFFICIAL</ins> AND IS MERELY THE RESULT OF AN EMPIRICAL TRIAL-AND-ERROR PROCEDURE.**

---

# About the printer
The Everes UNO's DLP projector is significantly more powerful (and hence faster) compared to other resin printers. This means that standard profiles for budget resins found online will be completely unusable.

Moreover, Everes printers are built to print only at predefined layer thicknesses (such as 50 μm, 100 μm, etc.). Therefore, you must calibrate every material with an allowed layer thickness value in mind. For each material, both 50 μm and 100 μm profiles are available.

Everes printers use a Smart Build Plate (SBP) that features holes. This implies that you cannot place objects directly onto the surface of the build plate; instead, you must suspend them using supports and orient them so they are NOT parallel to the SBP. 

---

# Materials and profiles
In the [**/support_center_settings**](./support_center_settings) folder, you can find the suggested CHITUBOX settings for raft, supports, and all related things.

In the [**/profiles**](./profiles) folder, you can find the profiles for the following water-washable standard resins:
- [Gray_WW Anycubic](https://www.amazon.it/dp/B07VXPGVNH?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
- [Clear_WW Anycubic](https://www.amazon.it/dp/B07VXQ3C15?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
- [SmokyBlack_WW Anycubic](https://www.amazon.it/dp/B0F83W8KFT?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)

If you wish to use a different material (or even a different color), you should start with a profile for a material that is as close as possible to the new one, and then adjust it by tuning the following parameters:

* **Bottom layer exposure time:** If the raft does not stick to the SBP, this time should be increased; if it sticks so hard that the *auto-detach* tool cannot remove it, the time should be decreased.
* **Exposure time:** If the supports are not strong enough, this time should be increased. If the supports are "overcooked" (i.e., they are too thick and coated with a "dirty" surface) or if you find a thin layer of partially polymerized resin at the bottom of the vat, the time should be decreased.
* **Picture grayscale:** The exposure time for the supports is intentionally set "too long" to make them more resistant. However, if the pixels curing the supports and those curing the part had the same brightness, the part would come out poorly. Therefore, a lower brightness is set for the pixels related to the part, while leaving the value at 255 for the supports. This will be noticeable after slicing in the grayscale photographs.
* **Light-off-delay:** This is the time between the moment the plate descends and the moment the next image is projected. This ensures the resin is completely still, preventing partially solidified resin from settling where it shouldn't. If the piece has a "dirty" surface, this time should be increased. If the piece has a very clean surface, you can try lowering it.

> [!TIP]
> Main LLMs are quite capable of giving helpful advice, but you must specify that the printer is a DLP system featuring a **tilting glass** and a VERY powerful projector. Otherwise, the answers will be based on standard "home" printers that use totally different profiles. You may also consider providing these profiles to the LLM as a starting point.

However, keep in mind that it will likely take a few dozen tests to dial in a new profile. In particular, pay attention to these points:
- To avoid confusion, you may want to start with a large light-off-delay (e.g., 3 to 4 seconds) and reduce it only once all other parameters are properly tuned.
- The raft should stick to the SBP reliably, but not excessively.
- Since you should not place objects directly on the build plate, it is not meaningful to verify whether the object itself sticks too much.
- The light should only cure the current layer, not the previous one. To check this, you can print a cube (height $\simeq$ 20 mm) with a small horizontal hole (radius $\simeq$ 4 mm) or the [snowflake](./snowflake.stl) (scaled down to 50%) and lower the exposure time and/or the picture grayscale.
- Since the 100 μm profile is harder to calibrate, you may want to calibrate the 50 μm one first (which is easier), and then feed it to an LLM to get an initial guess for the 100 μm settings.
- Since the 100 μm setting is faster (once properly tuned) and makes it easier to highlight light-off-delay issues, you might prefer to tune this final parameter on the 100 μm profile first, and then use an LLM's initial guess to adjust the 50 μm profile.

## Example pictures
In the [/pictures](./pictures) folder, you can find examples of pieces exhibiting various printing issues.

---

# Notes about the *tag holder*
As described in the printer manual, to use custom materials you must choose between using a *Custom* cartridge or using the *tag holder*.
- **When choosing the first option:** Take into account that the "Resin Name" field in the profiles must be filled with "Custom".
- **When choosing the second option:** Take into account that the "Resin Name" field in the profiles must be filled with "normal".

All the profiles provided here are configured for use with the **tag holder**. If you are using a custom cartridge instead, you must change the "Resin Name" field accordingly.


