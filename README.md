## Who will be the next NBA MVP winner?

Basketball is one of the most popular sports in the world, and NBA represents the highest level of playing the sport. So the MVP winner from NBA is the best player of the basketball in that year. I know everyone has their own MVP in their mind, but do you think it is possible using the stats of passing MVP to predict the future MVP?


## Data Description 

All the stats used in this project are obtained from [Basketball reference](https://www.basketball-reference.com/leagues/NBA_2019_per_game.html). There are three sets of data used in this project. First one is named MVP which is included pass years' MVP winners and some non-MVP players. This dataset is used to train the model which I will use to predict the MVP winner. The other two datasets are the stats of all players in season 2018 and season 2019(As of Nov 30th). The stats included the name of player, age, team, game played, points per game, assists per game, steals per game, blocks per game, percent field goals, percent three points, percent free throws, win share, win share per 48 minutes, and overall percent team wins.


## Explore the Data

Before we deciding on what kind of model is suitable for our prediction of MVP, I graphed the data to visualize the diffferences between MVP and the non-MVP. The following code was used:

```yml
sns.pairplot(mvp, x_vars=['PTS','WS/48','MP','TW','G%','G','Age','WS'], y_vars='Title', height=7, aspect=0.7)
```

The relationship shows as follow: 
![alt text](https://github.com/baitongc/Chen-Project/blob/master/photo/data.png "relationships")

From the visulization of the relationships, I think the factors impact on MVP winners are points, WS, WS/48, minutes played per game, percent team wins, and game played. 


## Model the Data

Two different models used to predict the future MVP. The first one is Support-Vector Clustering(SVC) with the poly kernel. By changing the gamma value, the model could have a better accuracy. I used 37 MVP winners and 46 non-MVP with all the factors I have to fit the model. The other model I used is logistic regression which I have chosen the factors with higher impacts based on the visulization during the explore the data. 


## As of Result

First I used both model to "predict" the MVP winner in 2018 season which we already know is Giannis Antetokounmpo. By using SVC with a gamma of 0.002( the best gamma I could find manually), the model predicted 4 players could be the MVP which included Giannis the MVP, James Harden, Nikola Jokic, and Damian Lillard. All four of them were actual MVP canadids from last season.

![alt text](https://github.com/baitongc/Chen-Project/blob/master/photo/svc2018.png "prediction with SVC")














```yml
title: [The title of your site]
description: [A short description of your site's purpose]
```

Additionally, you may choose to set the following optional variables:

```yml
show_downloads: ["true" or "false" to indicate whether to provide a download URL]
google_analytics: [Your Google Analytics tracking ID]
```
You can take a look at the `_config.yml` file in this repository to see how to type in the title and description.

### Markdown

You can see this [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) to work with Markdown language for adding features into this website.  This includes how to add headers, organization (e.g., bullets or lists), tables, and images.  It also includes how to add code to a website.

*Note that for images, you will need to place the image file in a place that it can be referenced and called.  I would suggest the github repo might be a good solution.  Often, I make an images folder and can call the raw images file.

See example [here](https://github.com/pages-themes/slate/blob/master/index.md).  You can see the raw code also.

#### Relative Links
To create links to other pages, you can read this article:  https://github.blog/2016-12-05-relative-links-for-github-pages/.  Note that these pages should by default direct to the same local folder/directory the index file is.  In this case, my README.md file is my index. If the files are in a different folder, one should specifiy the path for that folder.

### Notebooks

You can use a website to host notebooks.  First, you'll want to get the "raw" url from Github where your notebook is stored.  Then, navigate to https://nbviewer.jupyter.org and paste that URL.  The result will be a new generated URL that hosts your notebook.  This can be a [link](https://nbviewer.jupyter.org/github/isu-abe/516x/blob/master/module2/bootcamp/notebooks/nocode/Module%20IIB%20-%20Python%20Basics%20-%20no%20code.ipynb) in your website.

## Suggestions for Project Reporting

### Interesting question 

What is the scientitifc goal?  What would you do if you had all the data?  What do you want to predict or estimate?  Why is this relevant to ABE researchers or the field?  Provide some background on the rationale and relevance.

### Data description

What kind of data is avialble?  How is your data collected?  Are there any concerns about the data?  Which data is the most relevant?  Is the data easy to acccess? Will the data change over time?  What needs to be done to the data to get it ready for any downstream analysis?

### Explore the data

Demonstrate what you would do to describe the data and if it has any patterns or anomolies.  Make some plots.

### Model the data

Build a model, fit the model, validate the model.

### Communciate and visualize the results

What did you learn and do the results make sense?  Revisit your initial question and answer it.  H

### Class Exercise

In each project, I'd like to see a homework assignment that the class can do/evaluate to learn more about your data.  This should be a reproducible notebook that allows them to learn one or more aspects of your data workflow.  It is also an opportunity to share your research with your colleagues.

Here is an example of a fantastic project website:

https://stephenslab.github.io/ipynb-website/

## Advanced Features

### Stylesheet (Advanced)

If you'd like to add your own custom styles:

1. Create a file called `/assets/css/style.scss` in your site
2. Add the following content to the top of the file, exactly as shown:
    ```scss
    ---
    ---

    @import "{{ site.theme }}";
    ```
3. Add any custom CSS (or Sass, including imports) you'd like immediately after the `@import` line

*Note: If you'd like to change the theme's Sass variables, you must set new values before the `@import` line in your stylesheet.*

### Layouts (Advanced)

If you'd like to change the theme's HTML layout:

1. [Copy the original template](https://github.com/pages-themes/slate/blob/master/_layouts/default.html) from the theme's repository<br />(*Pro-tip: click "raw" to make copying easier*)
2. Create a file called `/_layouts/default.html` in your site
3. Paste the default layout content copied in the first step
4. Customize the layout as you'd like

### Overriding GitHub-generated URLs (Advanced)

Templates often rely on URLs supplied by GitHub such as links to your repository or links to download your project. If you'd like to override one or more default URLs:

1. Look at [the template source](https://github.com/pages-themes/slate/blob/master/_layouts/default.html) to determine the name of the variable. It will be in the form of `{{ site.github.zip_url }}`.
2. Specify the URL that you'd like the template to use in your site's `_config.yml`. For example, if the variable was `site.github.url`, you'd add the following:
    ```yml
    github:
      zip_url: http://example.com/download.zip
      another_url: another value
    ```
3. When your site is built, Jekyll will use the URL you specified, rather than the default one provided by GitHub.

*Note: You must remove the `site.` prefix, and each variable name (after the `github.`) should be indent with two space below `github:`.*

For more information, see [the Jekyll variables documentation](https://jekyllrb.com/docs/variables/).


### Contributing (Advanced)

Interested in contributing to Slate? We'd love your help. Slate is an open source project, built one contribution at a time by users like you. See [the CONTRIBUTING file](docs/CONTRIBUTING.md) for instructions on how to contribute.

### Previewing the theme locally

If you'd like to preview the theme locally (for example, in the process of proposing a change):

1. Clone down the theme's repository (`git clone https://github.com/pages-themes/slate`)
2. `cd` into the theme's directory
3. Run `script/bootstrap` to install the necessary dependencies
4. Run `bundle exec jekyll serve` to start the preview server
5. Visit [`localhost:4000`](http://localhost:4000) in your browser to preview the theme

### Running tests

The theme contains a minimal test suite, to ensure a site with the theme would build successfully. To run the tests, simply run `script/cibuild`. You'll need to run `script/bootstrap` one before the test script will work.
