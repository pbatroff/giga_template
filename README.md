# GIGA templates for Newsstore Mailings


## Notes on setting up development environment.

Mosaico provides a tool for generating thumbnails of the blocks.

The following worked with node 8.11.3, yarn 1.7.0

    git clone git@github.com:veda-consulting/uk.co.vedaconsulting.mosaico.git
    git clone -b "v0.15-civicrm-2" 'https://github.com/civicrm/mosaico' packages/mosaico # ./bin/setup.sh -D does this but with npm
    cd packages/mosaico
    yarn install           # takes ages.
    yarn add grunt-cli
    # You can now check makeThumbs works:
    # yarn run grunt makeThumbs:main:versafix-1
    git clone git@github.com:pbatroff/giga_template.git giga_template
    cd templates; ln -s ../giga_template/versafix-giga ; cd -
    # We can now build the thumbs in our custom template with:
    yarn run grunt makeThumbs:main:versafix-giga

    # Copy to server with:
    rsync -arv --exclude=".git" giga_template/versafix-giga/  giga:pro/sites/default/files/civicrm/mosaico_tpl/versafix-giga/

