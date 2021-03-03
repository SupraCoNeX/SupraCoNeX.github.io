# SupraCoNeX Website

## Running the setup locally

You can either install hugo locally on your machine or clone the docker image

```
docker pull docker.pkg.github.com/ikstream/hugo-docker/hugo:latest
```

## Creating new posts

To create a new post in `mab` run

```
hugo new post/mab/<title-of-new-post>/<title-of-new-post>.md
```
You can modify the newly created file now. First change the
`parent: <section>-news` to the actual topic. 
In the `mab` example this would be `parent: mab-news`. <br>
This will sort the new post in the according section in the overview.

After adding some content you can run hugo to check, if your article
meets your expectations. Therefore you need to set `draft: false` and run 
`hugo serve` or run `hugo serve -D` if you want to keep the draft status
of your article


To add one image to the top of all posts of a topic just place a hero.svg in
the root of that topic.

For an individual image for a post create a directory in that topic for that
post and place a `hero.svg` there, as well as the post's markdown file
