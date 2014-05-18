WP CLI HELPERS
==============

## Description
WP-CLI Helpers is a bundle of shell time saver aliases and function for wp-cli (http://wp-cli.org/).

## Examples

- run `cdwpt` to switch to theme directory
- run `cdwpp` to switch to plugin directory
- run `wpcdl` to download wp and choose your locale (language)
- run `wpci` to quickly install WP with default options
- run `wph` followed by any argument(s) to run `wp $myarg(s) --help`
- run `wppli $plugin_slug` to quickly install a plugin $plugin
- run `wpoa` to add an option with a prompter
 
### Video demos :
See it in action with these short videos :
- [Install wordpress in less than one minute with wp-cli ](https://www.youtube.com/watch?v=UH7gPxQm_1s&index=3&list=PLNKPjf-nKdiaon_IV3r6EI71IdcQ8_nZC
)
- [wp rewrite rule in 30 seconds with wp-cli ](http://www.youtube.com/watch?v=XhbRkyMww5U&feature=share&list=PLNKPjf-nKdiaon_IV3r6EI71IdcQ8_nZC&index=2)
- [Manage wordpress options in an eye blink](http://youtu.be/dECMEPvTT-c)



## Installation
Run `wpget https://github.com/kartonnade/wp_cli_helpers/archive/master.zip` or `curl https://github.com/kartonnade/wp_cli_helpers/archive/master.zip` or [download wp_cli_helpers as a zip file](https://github.com/kartonnade/wp_cli_helpers/archive/master.zip).
Plug all the scripts in a folder such as "wp_cli_helpers" in your $HOME directory and source the main file from your .bash_profile like so :

````
if [ -f "${HOME}/wp_cli_helpers/.wp_cli_helpers" ] ; then
 source "${HOME}/wp_cli_helpers/.wp_cli_helpers"
fi
````

# Details

#### [WP DB](https://github.com/kartonnade/wp_cli_helpers/blob/master/wp_core)

````
alias wpdbd=wp_db_drop
alias wpdbc=wp_db_create
````

#### [WP REWRITE](https://github.com/kartonnade/wp_cli_helpers/blob/master/wp_core)
Manage rewrite rules by simply running `wprwr`


#### [WP OPTIONS](https://github.com/kartonnade/wp_cli_helpers/blob/master/wp_core)
````
alias wpog="wp option get $1"
alias wpou="wp option update $1 $2"
alias wpod="wp option delete $1"
alias wpoa=wp_option_add
alias wpfront="wp option update page_on_front $1"
alias wpfrontpage="wp option update show_on_front page"
alias wpfrontpost="wp option update show_on_front post"
````


#### [WP CORE](https://github.com/kartonnade/wp_cli_helpers/blob/master/wp_core)
````
alias wpcdl=wp_core_download
alias wpcc=wp_core_config
alias wpci=wp_core_install

alias cdwp=go_to_wp_home_dir
alias wpd=open_wp_home_page_in_browser
````

#### [WP CORE DOWNLOAD](https://github.com/kartonnade/wp_cli_helpers/blob/master/wp_core)

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

#### [WP HELP](https://github.com/kartonnade/wp_cli_helpers/blob/master/wp_core)

````
alias wph="wp $1 --help"
alias wphc="wp core $1 --help"
alias wphr="wp rewrite $1 --help"
alias wphsr="wp search-replace $1 --help"
alias wphcc="wp cache $1 --help"
alias wphdb="wp db $1 --help"
alias wphm="wp menu $1 --help"
alias wpho="wp option $1 --help"
alias wphpl="wp plugin $1 --help"
alias wpht="wp theme $1 --help"
alias wphu="wp user $1 --help"
alias wphp="wp post $1 --help"
alias wphmloc="wp menu location $1"
alias wphmls="wp menu list $1"
````
#### [WP THEME](https://github.com/kartonnade/wp_cli_helpers/blob/master/wp_core)

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
alias wptd=go_to_theme_dir
alias wpatd=go_to_active_theme_dir
````

#### [WP PLUGIN](https://github.com/kartonnade/wp_cli_helpers/blob/master/wp_core)

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


## ALL ALIASES
````
alias wp_acf='wppli advanced-custom-fields; wppla advanced-custom-fields'
alias wp_seo='wppli advanced-custom-fields, wppla advanced-custom-fields'
alias wpatd='go_to_active_theme_dir'
alias wpcc='wp_core_config'
alias wpcdl='wp_core_download'
alias wpci='wp_core_install'
alias wpd='open_wp_home_page_in_browser'
alias wpdbc='wp_db_create'
alias wpdbd='wp_db_drop'
alias wpfoundationpress='git clone https://github.com/olefredrik/FoundationPress.git;'
alias wpfront='wp option update page_on_front '
alias wpfrontpage='wp option update show_on_front page'
alias wpfrontpost='wp option update show_on_front post'
alias wph='wp  --help'
alias wphc='wp core  --help'
alias wphcc='wp cache  --help'
alias wphdb='wp db  --help'
alias wphm='wp menu  --help'
alias wphmloc='wp menu location '
alias wphmls='wp menu list '
alias wpho='wp option  --help'
alias wphp='wp post  --help'
alias wphpl='wp plugin  --help'
alias wphr='wp rewrite  --help'
alias wphsr='wp search-replace  --help'
alias wpht='wp theme  --help'
alias wphu='wp user  --help'
alias wpmc='wp menu create '
alias wpmla='wp menu location assign '
alias wpmll='wp menu location list '
alias wpmlr='wp menu location remove '
alias wpmls='wp menu list '
alias wpoa='wp_option_add'
alias wpod='wp option delete '
alias wpog='wp option get '
alias wpou='wp option update  '
alias wppal='wp post list --post_type=page '
alias wppcff='wp_post_create_from_files'
alias wppdl='wp_post_delete'
alias wppfc='wp_post_file_create'
alias wppg='wp_post_generate'
alias wppl='wp plugin '
alias wppla='wp plugin activate '
alias wpplda='wp plugin deactivate '
alias wpplg='wp plugin get '
alias wppli='wp plugin install '
alias wppll='wp plugin list'
alias wpplpath='wp plugin path '
alias wppls='wp plugin status '
alias wpplsearch='wp plugin search '
alias wpplun='wp plugin uninstall '
alias wpplup='wp plugin update '
alias wppol='wp post list --post_type=post,wppolpage '
alias wpreverie='git clone wpgit@github.com:kartonnade/reverie.git'
alias wprwr='rewrite_rules'
alias wpt='wp theme '
alias wpta='wp theme activate '
alias wptd='go_to_theme_dir; wpts'
alias wptdel='wp theme delete '
alias wpte='wp theme enable '
alias wptl='wp theme list'
alias wptpath='wp theme path '
alias wpts='wp theme status '
alias wptsearch='wp theme search '
alias wptup='wp theme update '

````
````
````
````
````
````
````
