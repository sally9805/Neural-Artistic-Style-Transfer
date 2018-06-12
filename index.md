## Abstract

### Motivation
We want to use machine learning programs to transfer daily pictures to artistic style images by using a style image for obtaining the transferred style and a content image which we want to transfer the style onto. This project can demonstrate how well machine learning techniques perform on image processing and how artificial intelligence can, to some extent, achieve considerable success in the field of art and creativity.
<p align="center">
  <img src="images/prisma.webp" width="40%"><br />
  <i>Prisma style transfer image</i>
</p>  

Current style tranfer technques such as Prisma emphasized more on the color and layouts of style image. Hence, the synchronized image might lose the color and distort the outline of the content image. In our project, we would like to explore a technique that could keep the features of content images as well as apply artistic styles from style images.   

### Approach
We used convolutional neural network, specifically [*VGG19 model* in *Keras* library](https://keras.io/applications/#vgg19) in *Python*, for the implementation. The data set we used for this project consists of two sets of images: style images and content images. We have selected 40 famous paintings as style images. To transfer artistic style from paintings to content images, we include 4 images for testing: two of them are sceneries and the other two are portraits. 

### Result
In summary, we found that convolutional neural network performed very well on this task due to its outstanding performance on analyzing visual imagery. We have acquired decent synthesized images using CNN model with tuned parameters.  

<p align="center">
  <img src="images/deer_jp1.png" width="500px"><br />
  <i>Figure 1: Kanagawa Waved Deering</i>
</p>  

<p align="center">
  <img src="images/robert_por7.png" width="500px"><br />
  <i>Figure 2: Le Rêve Robert Downey Jr.</i>
</p>     

Since CNN utilized Max Pooling as downsampling strategy, when the image contains large contrastive color blocks in different areas, CNN will perform the best. In our examples, when the style image has big blocks of colors such as *Le Rêve* by *Picasso* in Figure 2, we observed the most decent results. On the contrary, if the style image is too colorful with small blocks of various colors as in Figure 3, the synthesized image will contain messy strokes and the layout of the colors will be chaotic.   

<p align="center">
  <img src="images/deer_abs6.png" width="500px"><br />
  <i>Figure 3: Fragmented Deering</i>
</p>     

According to our observation, we recommend to select style images with simple outlines and big blocks of colorful blushes for artistic style transfer and to avoid selecting paintings with too many colors.

### Contact Us
Haishan Gao -   B.S in Computer Science   - haishangao2020@u.northwestern.edu     
Jiajia Luo  - B.S in Computer Engineering - jiajialuo2018@u.northwestern.edu     

## Project Introduction

### Methodology
We use the pre-trained [*VGG19*](https://keras.io/applications/#vgg19) convolutional neural network model from Keras library in Python for our implementation due to its stability and reliability. The model requires a style image and a content image as inputs, and a noise image for optimization. During the optimization process, the code runs *scipy*-based optimization (L-BFGS) over the pixels of the generated image to minimize a loss value calculated by weighting content and style losses (the representation of "loss value" is introduced in the next section). Finally, the noise image will be optimized into a synchronized image which has content of the content image and a similar style from the style image.   
You can refer to the source code [here](Final_project_Style_transfer.ipynb).

### Feature Representation
The style or content representation of an image is measured by the output of a specific layer of the neural network. We have iterated through several layers to find the optimal one for output. 
In order to measure the similarity of the style/content of two images, we further define values “style loss” and “content loss” between the processed image and the input images, with less “loss” meaning the images more similar in style and content, respectively. Content loss is measured by passing both the synthesized image and the content image through some layers of the model and finding the Euclidean distance between the intermediate representations of those images; while style loss is measured similarly by comparing instead the **Gram matrices** of the outputs at various layers. (*A Gram matrix results from multiplying a matrix with the transpose of itself and contains non-localized information about the image, such as texture, shapes, and weights - which we defined as “style” representation in
our case.*)

### Data Collection
The data set consists of two types of images: style image and content image. We collected approximately one hundred representative paintings and selected 40 of them as the style image data set for our project. We then assigned them into 8 different categories: xx xx. For content images, we include two portraits and two sceneries since we observed that the results might differ when we used different images as content image.
We applied 40 style image for each content image and we ran 5 iterations of optimization for each pair. Hence, we obtained 800 photos in total in out final data set.
<p align="center">
  <img src="images/all40style.jpg" width="200px"><br />
  <i>Figure 4: Style Image Data Set</i>
</p> 

<p align="center">
  <img src="images/train_notext.png" width="500px"><br />
  <i>Figure 5: Content Image Data Set</i>
</p>

*Figure 3: Five iterations for each style-content pair*
### Evaluation
We include both quantative and qualitative evaluations for the results retured by the model. For qualitative evaluation, we simply evaluate the synthesized images manually. For quantative evaluation, we use the specific weighted loss values returned after each iteration of optimization.  

### Findings

You can use the [editor on GitHub](https://github.com/sally9805/eecs349project/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/sally9805/eecs349project/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
