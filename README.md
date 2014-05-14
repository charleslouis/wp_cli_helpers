WP CLI HELPERS
==============

### Description
WP-CLI Helpers is a bundle of time saver aliases and function for wp-cli (http://wp-cli.org/).

### Examples

- run `cdwpt` to switch to theme directory
- run `cdwpp` to switch to plugin directory
- run `wpcdl` to download wp and choose your locale (language)
- run `wpci` to quickly install WP with default options
- run `wph` followed by any argument(s) to run `wp $myarg(s) --help`
- run `wppli $plugin_slug` to quickly install a plugin $plugin
- run `wpoa` to add an option with a prompter
 
See it in action with these short videos :
- [Install wordpress in less than one minute with wp-cli ](https://www.youtube.com/watch?v=UH7gPxQm_1s&index=3&list=PLNKPjf-nKdiaon_IV3r6EI71IdcQ8_nZC
)
- [wp rewrite rule in 30 seconds with wp-cli ](http://www.youtube.com/watch?v=XhbRkyMww5U&feature=share&list=PLNKPjf-nKdiaon_IV3r6EI71IdcQ8_nZC&index=2)
- [Manage wordpress options in an eye blink](http://youtu.be/dECMEPvTT-c)



### Installation
Plug all the scripts in a folder such as "wp_cli_helpers" and source the main file from your bash_profile like so :

````
if [ -f "${HOME}/wp_cli_helpers/.wp_cli_helpers" ] ; then
 source "${HOME}/wp_cli_helpers/.wp_cli_helpers"
fi
````

# Details

## WP THEME HELPERS
````
alias wpt="wp theme $1"
alias wpta="wp theme activate $1"
alias wpte="wp theme enable $1"
alias wptd="wp theme disable $1"
alias wptdel="wp theme delete $1"
alias wptl="wp theme list"
alias wptup="wp theme update $1"
alias wpts="wp theme status $1"
alias wptpath="wp theme path $1"
alias wptsearch="wp theme search $1"

alias wpreverie="cdwpt; git clone https://github.com/milohuang/reverie.git;"

go_to_theme(){
	theme_path=$(wp theme path)
	cd $theme_path
}
alias cdwpt=go_to_theme
````

## WP PLUGIN

````
alias wppl="wp plugin $1"
alias wpplg="wp plugin get $1"
alias wppla="wp plugin activate $1"
alias wpple="wp plugin enable $1"
alias wppld="wp plugin disable $1"
alias wppldel="wp plugin delete $1"
alias wppll="wp plugin list"
alias wpplup="wp plugin update $1"
alias wppls="wp plugin status $1"
alias wpplpath="wp plugin path $1"
alias wpplsearch="wp plugin search $1"

alias wpplgacf="wpplg  'Advanced Custom Fields'; wpplg advanced-custom-field-repeater-collapser"

go_to_plugin(){
	plugin_path=$(wp plugin path)
	cd $plugin_path
}
alias cdwppl=go_to_plugin
````

## WP CORE DOWNLOAD

````
wp_core_download() {
	download="wp core download "
	read -p "Which locale (language) do you need ? (fr=fr_FR / en=en_EN) | default=en_EN : " -n 2 -r
	echo    # (optional) move to a new line
	if [[ $REPLY = "fr" || "FR" ]]
	then
	    download=$download' --locale=fr_FR'
	fi
	eval $download;
}
````
````
````
````
````
````
````
````
````
````
````
````
````
