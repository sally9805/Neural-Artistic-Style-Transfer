## Abstract
### Motivation
We want to use machine learning programs to transfer daily pictures to artistic style images by using a style image for obtaining the transferred style and a content image which we want to transfer the style onto. This project can demonstrate how well machine learning techniques perform on image processing and how artificial intelligence can, to some extent, achieve considerable success in the field of art and creativity.
<p align="center">
  <img src="images/prisma.webp" width="40%"><br />
  <i>Prisma style transfer image</i>
</p>

### Approach
We used convolutional neural network, specifically VGG model, for the implementation.The data set we used for this project consists of two sets of images: style images and content images. We have selected 40 famous paintings as style images. To transfer artistic style from paintings to content images, we include 4 images for testing: two of them are sceneries and the other two are portraits. 
### Result
We have acquired decent synchronized images using model with tuned parameters. 
*Figure 1:*
*Figure 2:*
We found convolutional neural network has outstanding performance on image processing. 
The style or content representation of an image is measured by the output of a specific layer of the neural network.
In order to measure the similarity of the style/content of two images, we further define values “style loss” and “content loss” between the processed image and the input images, with less “loss” meaning the images more similar in style and content, respectively. Content loss is measured by passing both the synthesized image and the content image through some layers of the model and finding the Euclidean distance between the intermediate representations of those images; while style loss is measured similarly by comparing instead the Gram matrices[1] of the outputs at various layers.
### Contact Us
Haishan Gao -   B.S in Computer Science   - haishangao2020@u.northwestern.edu
Jiajia Luo  - B.S in Computer Engineering - jiajialuo2018@u.northwestern.edu

## Project Introduction
### Model
### Features
### Data
The data set consists of two types of images: style image and content image. We collected approximately one hundred representative paintings and selected 40 of them as the style image data set for our project. We then assigned them into 8 different categories: xx xx. For content images, we include two portraits and two sceneries since we observed that the results might differ when we used different images as content image.
We applied 40 style image for each content image and we ran 5 iterations of optimization for each pair. Hence, we obtained 800 photos in total in out final data set.
*Figure 1: Style Image Data Set*
*Figure 2: Content Image Data Set*
*Figure 3: Five iterations for each style-content pair*

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
