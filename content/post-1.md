---
title: "Reading through the clouds"
date: 2021-05-26T13:37:00+00:00
# weight: 1
aliases: ["/reading-through-the-clouds"]
tags: ["posts","Northsec-2021"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: false
TocOpen: false
draft: false
hidemeta: false
canonicalURL: "https://ecapson.github.io/reading-through-the-clouds"
disableHLJS: true # to disable highlightjs
disableShare: false
#disableHLJS: false
hideSummary: true
searchHidden: true
ShowReadingTime: false
ShowBreadCrumbs: true
ShowPostNavLinks: false

#cover:
#    image: "../static/reading_through_the_clouds.png" # image path/url
#    alt: "<alt text>" # alt text
#    caption: "<text>" # display caption under cover
#   relative: false # when using page bundles set this to true
#   hidden: true # only hide on current single page
#editPost:
#    URL: "https://github.com/<path_to_repo>/content"
#    Text: "Suggest Changes" # edit text
#    appendFilePath: true # to append file path to Edit link

---

For this challenge, the following description and a link to an image was given.

	Up to the sky, I draw inspiration
	From the sun, I warm up my passion

	My ballads follow the birds songs
	The stars spell words to who my heart longs

	But these clouds make me raving confused.
	Would you kindly act as my decoding muse?

|![challenge](/reading_through_the_clouds.png#center)|
|:-:|
|Challenge Image|

At first, it was classified as steganography and before I touched the challenge, most steganography techniques were tried.
Since the image is pretty small, it was clear it wasn't steganography.
Looking at the image, you can almost tell that it's blurred text due to the spacing and coloring. 
Which reminded me a tool from a while ago: https://github.com/beurtschipper/Depix

There was no context clues to what kind of font were used, but we can try common scenarios. Depix provides few scenarios.
So we try them all:

```ls images/searchimages/ | xargs -I {} sh -c "python depix.py -p reading-through-the-clouds.png -s images/searchimages/{} -o chall/output_{}"```


|![](/output-win7.png)|
|:-:|
|notepad Windows 7 close|

Hmm :thinking: not very readable.

|![](/output-win10close.png)|
|:-:|
|notepad Windows 10 close|

Much better but we can do better

|![](/output-win10-cs.png)|
|:-:|
|notepad Windows 10 close and spaced|

Not perfect, but we can tell that it says
	
	the secret is lastkingdom
	
The secret was indeed lastkingdom and we get some points.
![](/reading_through_the_clouds-points.png)

## Conclusion
|![](/one-does-not-simply-enhance-the-image.jpg)|
|:-:|
|with few exceptions :wink:|

