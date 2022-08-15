# css-foundations-project

## Project hosted at: https://goldsmithb.github.io/css-foundations-project/

## Citations
### Fonts
Robot Flex : https://fonts.google.com/specimen/Roboto+Flex#about
Valera Round : https://fonts.google.com/specimen/Varela+Round#about

## Images
Blue Jeans (intro panel) : https://pngimg.com/image/5768
Sonic (info) : https://play.google.com/store/apps/details?id=com.sega.sonicdash&hl=de&gl=US
Mario (info panel) : https://supermariorun.com/en/index.html
Figaro (info) : https://www.google.com/url?sa=i&url=https%3A%2F%2Foperaspace.org%2Fopera%2Fthe-marriage-of-figaro%2F&psig=AOvVaw3-c2uuOZGrI3YV4JXij0py&ust=1652877180379000&source=images&cd=vfe&ved=0CA0QjhxqFwoTCPjkssHF5vcCFQAAAAAdAAAAABAl
Hatsune Miku (info) : https://play.google.com/store/apps/details?id=com.sega.ColorfulStage.en&hl=en_GB&gl=US

## Strugles and Outcomes
Resizing images dynamically while maintaining aspect rations:
This was a problem I encountered a few times during the project, especially when working on the card images.
I wanted the images and the descriptions to resize a little when the user resizes the window. The width should shrink to at most 100px and grow to a max of 180px.
The main div (#info) is a flex container containing the cards, using flexbox to space the items.
I set the minimum and maximum widths on these cards (flex-items of the #info div). This garauntees that the cards themselves will grow and shrink appropriately. However, I now needed to make sure my images were growing and shrinking inside the card, so each card had to be a flex container as well.
I knew that for an image element flex-item to grow/shrink, it needs a set height and auto width (or vice-versa). However, I also needed these images to be cropped to squares, which I knew how to do using the width, height, and object-fill properties. But I had a problem: how can I make sure the item can resize appropriately but also stay cropped using flexbox?



This was related to a larger question: should I wrap elements in \<div\>s when I make flex items? Or shouldn't I just be able to treat all flex-items similarly regardless of what element they are?
I was certain it should be allowed, but I had a feeling behavior would be different. This was something I had to be aware of when debugging as well: were the examples and solutions I was reading through appropriate for the problem I was having?
I found that there were two ways to scale an image how I wanted: set the width and height to 100% of the container so that it scales as the container (a flex item) is resized, or set the image itself as a flex item with auto width and height and align-self set to non-stretch.
https://stackoverflow.com/questions/54071620/why-does-wrapping-an-image-with-a-div-in-a-flexbox-scale-it-correctly-but-img-it

Font problems: I can't find a font that behaves how I want. Until I do a tutorial on how to use fonts properly, I will just use sans-serif.
