googlemock
==========

Unofficial googlemock Clone https://code.google.com/p/googlemock/

Created by:

	# Import Svn Repository
	git svn clone --username=googlemock-read-only --prefix=upstream/ \
	              -s http://googlemock.googlecode.com/svn googlemock

	# Import Tags
	cd googlemock
	for tag in `git branch -r | grep "upstream/tags/" | sed 's/upstream\/tags\///'`; do
	  git tag -a -m"Converting SVN tags" $tag refs/remotes/upstream/tags/$tag
	done

	# Push to Origin
	git remote add origin git@github.com:istarc/googlemock.git
	git fetch --all
	git merge origin/master # Merge .gitignore and README.md
	git push --all origin
	git push --tags origin

Clone (no warranties):

    git clone https://github.com/istarc/googlemock.git

Update:

    git svn rebase

Checkout a tag:

    git tag -l
    git checkout release-1.7.0