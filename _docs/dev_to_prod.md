## Currently (2024-01-06)


FIRE UP YOUR UBUNTU VM FIRST!

On ubuntu, build site with `jekyll build` or `bundle exec jekyll serve --host 0.0.0.0 --livereload` to see it in action.

Push code to git hub before moving on.

Copy working site from ubuntu to local machine
	`scp -r ubuntu:ffblog/_site/* mac:~/Workspace/ffblog_prod/`

Copy local working code to production (sedna)
	`scp -r ~/Workspace/ffblog_prod/* sedna:public_html/`


hit `https://faberfedor.com` for testing
