# 📷 Sirosky's Super Resolution Models

A repository containing upscaling models I created for public use. Currently, there are only 2x models for anime, but I plan on training models for RL footage at some point as well.

![image](https://github.com/Sirosky/Sirosky-Upscaling-Models/assets/2752448/2b30654d-0a0e-42d6-a85f-0b087f622511)

*Comparison image for AniDVD.*

# ⏬ Released Models
*Ratings included for each model are meant to serve as a quick point of reference to see how the models differ.*

### **HD/FHD Sources - Ani4K**

As the name suggests, Ani4K is trained to create natural-looking 2K/4K upscales from 720p/1080p sources. In particular, the model has superb detail retention.

- **Detail Retention**: ⭐⭐⭐⭐⭐
- **Compression Cleanup**: ⭐⭐(will deal with compression in HD/FHD BD and WEB sources without a hitch, but struggles with DVDs-- use Anima or AniDVD for DVD sources)

### **Legacy Model - AniScaleV1**
    
My very first publicly released model. I consider it obsolete at this point, but some people might prefer the sharper look, so I'm releasing it here as well. As a first generation model, I trained AniScale to serve as a general-purpose model for all sources. Unfortunately, it simply isn't possible to have a single model do everything well-- subsequent generations of models are more specialized, and will do better for the sources they specialize in. While the model is great with details and dealing with a variety of video artifacts, it has a tendency to oversharpen some sources and background details. It doesn't handle blur at all either, though that's a problem common with many other anime models. 

# 📚 Model Training Principles

This section provides an overview of the guiding principles I follow while training my models. It should give a sense of whether these are the right models for you, and what sets my models apart from others.

**Balanced** **Sharpness**: While my models deblur and sharpen the input, they aren't the sharpest ones available. This is intentional-- the models aim to produce a *natural-looking* upscale, as if the result was something natively produced by the studio. In addition, oversharpening tends to produce undesireable artifacts.

![image](https://github.com/Sirosky/Sirosky-Upscaling-Models/assets/2752448/72b1a304-c880-4b2e-a7d5-04cb25bfda7e)

*Roof tiles so sharp that you can cut yourself on them*.

**Line Art** **Retention**: Retaining crisp line art is key to making anime upscales look pleasing to the eye. Some models, even those trained on modern anime, can produce "hallowed" lines (example below) at higher resolutions. My models are trained to retain / enhance line art, and of course, avoid the hallowed line effect.

![image](https://github.com/Sirosky/Sirosky-Upscaling-Models/assets/2752448/42915a42-24ed-445c-8054-eeb042e7a802)

*Note how the lines here don't seem solid. Sometimes, it's an artistic decision. But this example is the model not properly handling line art after oversharpening.* 🤢

**Detail Retention**: This largely speaks for itself-- you don't want a model that nukes textures and/or destroys details. While it's not always possible to achieve flawless detail retention (especially with models that have more-aggressive clean-up), detail retention is something that my models generally excel in.

![image](https://github.com/Sirosky/Sirosky-Upscaling-Models/assets/2752448/af1f4312-d12b-4d2b-9f2a-5ceb3dbdb74d)

*Where did the fence go?*
**Compression Clean-up**: This is self-explanatory as well. When upscaling, the model should clean up compression artifacts present in the source (haloing, noise, chroma bleed, etc.) rather than upscale the artifacts along with the rest of the picture. However, it is also important to not go overboard, as doing so comes at the expense of detail retention.

![image](https://github.com/Sirosky/Sirosky-Upscaling-Models/assets/2752448/516a3779-780a-45e4-975d-69258a944abd)![image](https://github.com/Sirosky/Sirosky-Upscaling-Models/assets/2752448/c3586dd8-1837-4598-9780-39685fa34509)

*On the left, an example of a model that upscaled but didn't fix the white haloing, vs. on the right, AniDVD which upscaled and cleaned* haloing.

**Depth of Field and Intentional Blur Retention**: DOF/blur effects are extremely common in modern anime, and present even in older anime. While it can be tempting to sharpen the crap out of everything on the screen (see AniScaleV1 below), such an approach can create odd-looking results when it brings into focus items that should be out of focus. Aside from AniScaleV1, which is the first model I ever released, all my models are trained to handle blur effects appropriately.

![image](https://github.com/Sirosky/Sirosky-Upscaling-Models/assets/2752448/e17dfda2-2c03-4bf1-acb9-a470bfc91644)![image](https://github.com/Sirosky/Sirosky-Upscaling-Models/assets/2752448/d4e67e4c-93b6-4ee0-9b0d-00906ed18962)

*Some things are better left blurred...*

**Upscaling Artifacts**: Some models produce upscaling artifacts-- blemishes on the image generated by the model during the upscaling process. These can vary from annoying to hardly noticeable, but in my book, it's best to avoid generating artifacts to begin with!

![image](https://github.com/Sirosky/Sirosky-Upscaling-Models/assets/2752448/89aae0d9-89bc-4d37-9ba1-34f0a91c6aab)![image](https://github.com/Sirosky/Sirosky-Upscaling-Models/assets/2752448/fe83561f-9ee8-4121-8988-88ff2ac8c9f1)

*An example of a fairly subtle artifact-- the white glow generated at the intersection of the two lines.*
