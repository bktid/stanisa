# Stanisa

## The start
* created a new repository
* went to settings and selected master branch as the source for the project page
* I can now add content directly in the root of the master branch
* Added index.html file with hello world heading
* Website is published under https://bktid.github.io/stanisa/

## Switching to Jekyll
* I needed a way to dynamically show the images in a subdirectory in html
* Found a solution that is based on indexing the subdir, but github doesn't support that
  * https://stackoverflow.com/questions/6994212/is-there-a-way-to-return-a-list-of-all-the-image-file-names-from-a-folder-using
  * https://stackoverflow.com/questions/18480550/how-to-load-all-the-images-from-one-of-my-folder-into-my-web-page-using-jquery
* Switched to Jekyll because Front Matter gives you access to static files
  * https://jekyllrb.com/docs/static-files/
  ```
  {% for image in site.static_files %}
    {% if image.path contains 'images/slider' %}
        <img src="{{ site.baseurl }}{{ image.path }}" alt="image" />
    {% endif %}
  {% endfor %}
  ```
  * Had to change the foldername to `pictures`, because jekyll spawns extra images in the `assets/images` folder :-)

## Lightbox
Used lightbox to create an image gallery using these sources:
* http://lokeshdhakar.com/projects/lightbox2/
* https://christianspecht.de/2014/03/08/generating-an-image-gallery-with-jekyll-and-lightbox2/
