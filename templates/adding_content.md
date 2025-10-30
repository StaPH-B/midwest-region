
# Adding new pages to Resources and Trainings
To add new pages to the Resources and Trainings sections of the website:

1. Make a copy of the `resources.md` or `trainings.md` markdown file found in the `templates/` directory and move it to the `_resources/` or `_trainings/` directory, respectively. 
2. Change `Resource title`/`Training title` to the title of your resource/training
3. Change `Resource description`/`Training description` to a brief description of the resource/training.
4. Update the `resource number`/`training number` according to those already present in the directory. For example, if there are five markdown files already present in the `_trainings/` directory, change the `training_number` to 6.
5.  Add your content to the markdown file according to markdown syntax. A training to markdown can be found [here](https://www.markdownguide.org/basic-syntax/). Any images you want to include should be placed in the `images/` directory and can be added using the syntax given in the following example: `![Paired_End](/images/paired_end.png "Paired End Sequencing")` Videos can be added using the syntax given in the following example: `{% include youtube.html id="1JnLBws7L70" %}`. In this example `1JnLBws7L70` is the string of characters found at the end of the YouTube URL where the video can be watched.
6. Rename the template file with a name corresponding to the resource's/training's title. 
7. Preview the changes using the command `bundle exec jekyll serve .` in the top of the repository's directory. Changes can be  previewed at the URL `http://localhost:4000/midwest-region/`
8. Commit changes and push to main branch.
