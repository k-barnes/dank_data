# Dank or Not

Supplementary data for the paper the _Dank or Not? -- Analyzing and Predicting Popularity of Memes on Reddit_ - Barnes et al. (2021)

## How to Cite

```
@article{barnes2021dank,
  title={Dank or not? Analyzing and predicting the popularity of memes on Reddit},
  author={Barnes, Kate and Riesenmy, Tiernon and Trinh, Minh Duc and Lleshi, Eli and Balogh, N{\'o}ra and Molontay, Roland},
  journal={Applied Network Science},
  volume={6},
  number={1},
  pages={1--24},
  year={2021},
  publisher={SpringerOpen}
}
```

## Source

The data is scraped using a [Pushshift API](https://pypi.org/project/psaw/), and it consists of all posts starting from March 17th, 2020 to March 23rd, 2020 across these Reddit subreddits:

- [MemeEconomy](https://www.reddit.com/r/MemeEconomy/),
- [dankmeme](https://www.reddit.com/r/dankmeme/),
- [memes](https://www.reddit.com/r/memes/),
- [me_irl](https://www.reddit.com/r/me_irl/),
- [dank_meme](https://www.reddit.com/r/dank_meme/) (this subreddit has gone private)

## Summary of Data

After cleaning, we end up with 80,362 posts that are used as training/testing data for our machine learning models. This [spreadsheet](./data/final_dank.csv) contains the posts with their metadata as well as the generated attributes we used in the paper.
| Feature | Type | Description |
|----------------------|-------------------------------|--------------------------------------------------------|
| created_utc | UTC timestamp | time of post submission |
| ups | integer | number of upvotes received |
| is_nsfw | boolean | indicates if only suitable for 18\+ |
| subreddit | string | subreddit of the submission |
| subscribers | integer | number of subscribers to the subreddit |
| thumbnail\.height | floating point value | height of the thumbnail |
| thumbnail\.thumbnail | string | thumbnail media |
| thumbnail\.width | floating point value | width of thumbnail |
| title | string | title of the submission |
| media | string | link to associated meme media |
| ups_normed | floating point value | ups normalized with subscribers |
| dank_level | integer | label ups_normed for binary classification |
| processed_words | list of strings | filtered and stemmed words from title and image |
| word_count | integer | number of words in title and image |
| TextLength | integer | number of characters in title |
| Sentiment | floating point value | text valence score |
| avg_hue | floating point value | average HSV hue value of meme |
| avg_saturation | floating point value | average HSV saturation value of meme |
| avg_value | floating point value | average HSV value value of meme |
| 30 colors | floating point value | normalized pixels of color in image |
| VGG_features | list of strings | VGG\-16's first three guesses about image content |
| VGG_probs | list of floating point values | the probabilities of the VGG\-16's first three guesses |

## Raw Image Files

For the Convoluted Neural Network section of the paper, we download and sample from the 76,000+ downloadable images provided in the media field of the posts. The raw image files can be found in the [data folder](./data).

|                | dank  | not_dank | Total |
| -------------- | ----- | -------- | ----- |
| Training set   | 1,856 | 1,856    | 3,712 |
| Validation set | 928   | 928      | 1,856 |
| Test set       | 929   | 929      | 1,858 |
| Total          | 3,713 | 3,713    | 7,426 |

## Random Forest

The notebook for the Random Forest model along with some supplementary analysis for the model can be found in the [notebook folder](./notebook).

A more detailed description of the dataset and how we generate our attributes can be found in [_Dank or Not? -- Analyzing and Predicting Popularity of Memes on Reddit_](https://appliednetsci.springeropen.com/articles/10.1007/s41109-021-00358-7)

## Image Analysis

The notebooks for the image analysis and features extraction can be found in the [notebook folder](./notebook).

Final plots and a more detailed description can be found in the Image Analysis section of [_Dank or Not? -- Analyzing and Predicting Popularity of Memes on Reddit_](https://appliednetsci.springeropen.com/articles/10.1007/s41109-021-00358-7)
