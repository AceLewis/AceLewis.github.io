---
layout: post
title:  "Image Formats and When to Use Them"
url-title: "Image Formats And When to Use Them"
date:   2016-01-06 14:00:00
author:
published: true
categories:
- blog

tags:
- images
- formats

img: image-types.gif
thumb: what-image-types.png
---

There are a few image formats used on the web, this blog post is aims the explain what each one is in simple terms and also explain the situations where each format is appropriate. Some people argue over what image format people should use (all the time) however it is much better to understand the situations where specific image formats should and shouldn't be used and the situations where people abuse formats.
<!--more-->

#### The Basics
Most images you see are Raster images (sometimes confusingly called bitmaps) they are made up of many pixels, each pixel has a colour that is displayed on the screen. The colours of each pixel is saved in a colour space it is not really important to know exactly what colour space is being used but you should know that all colours you see are reproduced with only three numbers. These three numbers represent different quantities e.g. Red, Green and Blue, or Hue, Saturation and Value, if transparency is needed the image then there would be an extra number often referred to as Alpha. What most image formats aim to do is get the best quality image using the smallest amount of bytes.

#### The Main Image Formats
The main formats I am going to cover are BMP, PNG, JPEG, GIF and GIFV. These are all raster graphic formats, I will also cover SVG a vector graphic format. I will also try to compare the different formats to show you when certain formats should and shouldn't be used.

#### Bitmap (BMP)
To clear any ambiguity as Raster images are sometimes referred to as bitmap images I am talking about the BMP file format. A bitmap is the simplest image format available it stores the colour value of each pixel with an optional transparency layer. BMPs often don't use transparency so only use RGB (Red, Green and Blue) to store colours, images can be compressed but often are not and the file has the size of the image and the colour at each pixel. As the image is not compressed it is very simple to process and is a lossless image format meaning that by saving an image in this format no quality is lost at all however the file sizes are very large so it is almost never used to store images or distribute them on the web.

#### Portable Network Graphics (PNG)
Portable Network Graphics also known as PNG is a lossless image format like BMPs however they are compressed. The compression applied to PNGs don't change the data so therefore don't change the image, it is similar to zipping and unzipping a file. One other way to compress PNGs before the comressiong algorithms are applied is by using indexed colour. Indexed colour means that it makes a big list of all the colours in an image and then when each colour in the list is used in an image it puts the location of the pixel in the list, as the colours in the list are made up of three numbers and only one number is needed to point to the location in the list you save on the amount of data needed to store the image. The size of the list and therefore the maximum size of the number used to point at the list is dependant on the number of colours in the image, you can reduce the file size even further by approximating the colours used and making the list smaller however this leads to lossy compression, this compression may be lossy however if you compare two images the difference is hard to notice.

To compare PNG compression to BMP I got a lossless PNG of Tux (the Linux kernel mascot) and then saved the image as a BPM (without transparency), the BMP image was 561 KB. The lossless PNG is 40.2 KB only 7.2% of the BPM showing that the PNG format can compress a raw image by a considerable amount. To compare the lossy against lossless PNGs I compressed the image of Tux using indexed colour and the final image was 17.9 KB that is only 44.5% of the lossless image, in the lossy image you can notice banding in the forehead of the penguin however this not that noticeable and would be perfect for a website as it saves a lot of bandwidth and speeds up the page load time.

<div class="title-half">
    <div><b>Tux PNG lossless (40.2 KB)</b></div>
    <div><b>Tux PNG lossy (17.9 KB)</b></div>
</div>

<div class="container-half">
   <img alt="Tux Lossless" src="/assets/img/blog/image-types/tux.png"/>
   <img alt="Tux Lossy" src="/assets/img/blog/image-types/tux-min.png"/>
</div>

You can create indexed PNGs using [pngquant](https://pngquant.org/){:target="_blank"}{{_}} (Free and [opensource](https://github.com/pornel/pngquant){:target="_blank"}{{_}}) however if you don't want to install that software to check it out you could use online services like [TinyPNG](https://tinypng.com/){:target="_blank"}{{_}} or [CompressPNG](http://compresspng.com/){:target="_blank"}{{_}}. I recommend [CompressPNG](http://compresspng.com/){:target="_blank"}{{_}} more as it easily allows you to manually tweak with the numbers of colours used in the indexing list.

Side note: Animated PNGs have existed since 2008 however browser support is lacking, [only Firefox and Safari 18% of the global browsers support animated PNGs](http://caniuse.com/#feat=apng){:target="_blank"}{{_}}.

#### JPEG
JPEG is the most commonly used image format on the internet, it can be used as lossless compression however it is mostly used for lossy compression. The idea behind it is the lost data is not that important for the image and the image will be perceptually lossless. As data is being lost it can compress images much more than PNGs however not in all circumstances, also a big downfall of JPEG is it does not support transparency at all unlike PNG. JPEG compression initially works by splitting the file up into many blocks of pixels usually 8 by 8, it then performs discrete cosine transforms (turns the image into waves) on the blocks of pixels and to compression is done by setting the smaller less needed numbers from the discrete cosine transform to zero (removing the small waves that don't contribute much) so the data is compressed considerably when Huffman encoding is applied. JPEG compression is bad for text as the straight lines get "fuzzy", also successive compression of a JPEG image deteriorate the quality considerably this is bad and is why some people dislike JPEG. Saving a JPEG using exactly the same compression as originally used does not reduce the quality as much (if at all) however when images are shared on the internet one image may be compressed by JPEG many times using all different compression tables (in the discrete cosine transforms) so images have blocky artifacts near edges, an example image is shown below of the text of an image that has been posted and reposted online. The fuzziness around the text is caused by this successive JPEG compression.

![JPEG text](/assets/img/blog/image-types/JPEG-text-comression.jpg){: .center-image }

This is a big problem for JPEG and is one reason why people dislike it, the image that has been compressed many times is probably bigger than the image after the first compression as the fuzziness is now part of the data the image is trying to compress. Also for text it could be much smaller if a indexed colour PNG is used as not that many colour would be present so it would be lossless and have a smaller file size.

A comparison of JPEG compression against PNG is shown below on the image of Tux, the PNG is slightly larger however it does also have a transparency layer unlike the JPEG. As you can see in the image the lossy PNG has a much better image quality, around sharp edges there are artifacts in the JPEG image along with the features being smoothed out unlike in the PNG. The JPEG compression problems is more apparent when you zoom in

<div class="title-half">
    <div><b>Tux lossy PNG (17.9 KB)</b></div>
    <div><b>Tux lossy JPEG (15.4 KB)</b></div>
</div>

<div class="container-half">
   <img alt="Tux lossy PNG" src="/assets/img/blog/image-types/tux-min.png"/>
   <img alt="Tux lossy JPEG" src="/assets/img/blog/image-types/tux-min.jpg"/>
</div>


<div class="title-half">
    <div><b>Tux lossy PNG eye zoomed in</b></div>
    <div><b>Tux lossy JPEG eye zoomed in</b></div>
</div>

<div class="container-half">
  <img alt="Tux lossy PNG eye" src="/assets/img/blog/image-types/tux-min-eye-png.png"/>
  <img alt="Tux lossy JPEG eye" src="/assets/img/blog/image-types/tux-min-eye-jpg.png"/>
</div>

This highlights the problems with JPEG however it does so unfairly...

JPEG is an acronym for Joint Photographic Experts Group, and as the name implies this compression format was made for the use with photographs of the real world not images of penguins made on a computer. JPEG compression excels in the compression of photographs and if the compression algorithm is applied only once the compressed image is almost indistinguishable from the initial picture. As JPEG is brilliant at compression photographs nearly all cameras save the images in this format meaning that it is difficult to get a raw photographic image that was initially save in a lossless format e.g. PNG. High end cameras can take images in "raw" however the final images are almost always distributed in JPEG format and the appeal to "shoot raw" is due to more control of the colour and exposure when editing the photograph afterwards. Photographs will tend to have much more than 256 colours so indexed PNGs can not be used, this is the main reason why images shared online tend to be in this format.

#### GIF
The GIF is an image format often used to share short moving images (without sound), most people online have seen GIFs used to show clips of cats or people falling over but that was not what they were intended for and it is not how they should be used. GIFs don't need to be moving images they just are images that similar to indexed PNGs they can only have 256 colours in the image, they then are compressed by a compression algorithm called Lempel–Ziv–Welch. Lempel–Ziv–Welch is a lossless compression algorithm however images will look bad as only 256 colours can be used so and images themselves are not losslessly compressed. Lempel–Ziv–Welch is not as good as DEFLATE the compression algorithm used by PNG so an indexed PNG would have a smaller file size, despite this GIFs have one big benefit over PNGs and JPEGs they can have moving images.

![Wow GIF](/assets/img/blog/image-types/wow.gif){: .center-image }

The reason why GIFs are still used is only because they allow the looping of moving images, it was initially intended for "cool" embedded email icons that you could embed into your HTML only website in the 1990's. The "Wow GIF" shown above would not look professional or even be used on any website now but if you can find old usually academic websites that do use GIFs in the way that they were intended e.g. [here](http://jila.colorado.edu/~ajsh/insidebh/index.html){:target="_blank"}{{_}}. Now GIFs are used to display videos with no sound however it is a really bad thing as each frame of the gif is a raw image so GIF videos tend to have huge file sizes and are often very slow to load. To reduce the file size GIFs tend to have a low frame rate, the bad image quality and blurred frames of a GIFs is shown below. (I don't want to embed a large GIF so you can see the GIF [on imgur.](http://i.imgur.com/q61ve2F.gif){:target="_blank"}{{_}})

![Bad GIF](/assets/img/blog/image-types/gif.png){: .center-image }

A bonus fact, GIFs don't need to loop they can be made to play just once however they are almost always used with the looping ability.

#### GIFV
GIFVs are the "solution" to the GIF problem, they have much smaller file sizes and therefore load much faster than traditional GIFs. GIFVs are just autoplaying and autolooping MP4 videos without audio and all video features like the pause, play, and the timeline removed. One big problem for GIFVs is they can't be embedded on a webpage in the same way on all devices, phones, tablets and many mobile devices however the image quality is much better and colors that can be used is much more than 256. Videos are much more efficient than showing individual pictures one after the other like in GIFs as they can use more complex compression that can rely on the frames easier in the video. (I don't want to branch out too much on that topic) GIFVs are great and solve the problems of GIFs, one slight benefit of GIFs is they require less computation to display as there is no compression however this is not an issue as I am not aware of a device that can connect to the internet and has the computational power to display GIFs but not videos, also the power used to download the GIF far out ways and power saved by the less complex computation.

#### SVG
Finally SVGs, all the other image types mentioned before are Raster image formats that store pixels in different ways SVGs are totally different. SVGs are the most used format Vector graphics, instead of storing the pixel values Vector graphics store instructions on how to make the image, for example place a circle here I want it this big and it needs to be blue. These instructions are then read by the browser or file viewer and the image is displayed. As SVGs are just instructions the files they produce can be very small when compared to PNGs or JPEGs. SVG stands for Scalable Vector Graphics and as the name implies the images produced are scalable meaning that you can zoom in or enlarge a SVG without causing and problems, the same SVG that is used for an icon on a website can be used and put on a giant billboard. If you took a PNG or JPEG image from a webpage and scaled it up to the size of a billboard it would look terrible as the pixels would be large enough to see however SVGs have no pixels only shapes.

SVGs are not only used for logos but are nearly always used for fonts, SVGs are perfect as they can be scaled to any size without loosing quality. Fonts are not limited to words and text either on this block the share buttons (Facebook, Reddit, ect.) are all fonts from [Font Awesome](http://fontawesome.io/){:target="_blank"}{{_}} not images so they have the benefit of not changing when people view the webpage on different devices. An example of what would happen to raster text when scaled up is shown below;

![Raster vs Vector](/assets/img/blog/image-types/Bitmap_VS_SVG.svg){: .center-image }

A extra feature of SVGs that is very underused is animations, complex 3D animations can be made however they are often not used as it is hard to embed them on webpages (you need to embed them on the page) one of this in use is [a spinning ball](http://debeissat.nicolas.free.fr/images_svg/ball_3d.svg){:target="_blank"}{{_}}. The downside of SVGs is some very old browsers don't support them, for example IE8 and before. In that case you can have a PNG or JPEG as a fallback to load for those people. Vector graphics are used in many online map websites like Google maps, the roads (not in satellite view) are SVGs as you can zoom in, not much data is needed to draw a road and they display correctly on many devices that support SVG.

#### Conclusion
The conclusion for this blog post is that JPEG is good for photographic images however repeated application of JPEG compression severely damages images, PNGs are a good lossless format and can be used in a lossy format to compress non photographic images better than JPEG. GIFs are not used for the purpose they are intended for so GIFVs (basically renamed MP4s) can in most cases be used to replace them. I also stated that SVGs are very good but only for their specific applications in fonts, maps and icons.
