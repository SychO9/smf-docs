# Available Hooks
?> 350+ Hooks

#### index.php
- integrate\_autoload (`&$classMap`)
- integrate\_pre\_log\_stats (`&$no_stat_actions`)
- integrate\_actions (`&$actionArray`)

#### SSI.php
- integrate\_autoload (`&$classMap`)
- integrate\_SSI
- integrate\_ssi\_queryPosts (`&$posts`)
- integrate\_ssi\_recentTopics (`&$posts`)
- integrate\_ssi\_topPoster (`&$return`)
- integrate\_ssi\_topBoards (`&$boards`)
- integrate\_ssi\_topTopics (`&$topics`, `$type`)
- integrate\_ssi\_queryMembers (`&$members`)
- integrate\_ssi\_boardStats (`&$totals`)
- integrate\_ssi\_whosOnline (`&$return`)
- integrate\_ssi\_recentPoll (`&$return`, `$topPollInstead`)
- integrate\_ssi\_showPoll (`&$return`)
- integrate\_ssi\_news
- integrate\_ssi\_calendar (`&$return`, `$eventOptions`)
- integrate\_ssi\_calendar (`&$return`, `$eventOptions`)
- integrate\_ssi\_calendar (`&$return`, `$eventOptions`)
- integrate\_ssi\_calendar (`&$return`, `$eventOptions`)
- integrate\_ssi\_boardNews (`&$return`)
- integrate\_ssi\_recentEvents (`&$return`)
- integrate\_ssi\_recentAttachments (`&$attachments`)

#### Sources/Admin.php
- integrate\_admin\_search (`&$language_files`, `&$include_files`, `&$settings_search`)
- integrate\_manage\_logs (`&$log_functions`)

#### Sources/Attachments.php
- integrate\_attachment\_upload

#### Sources/BoardIndex.php
- integrate\_mark\_read\_button

#### Sources/Calendar.php
- integrate\_calendar\_buttons

#### Sources/Display.php
- integrate\_display\_topic (`&$topic_selects`, `&$topic_tables`, `&$topic_parameters`)
- integrate\_poll\_buttons
- integrate\_display\_message\_list (`&$messages`, `&$posters`)
- integrate\_query\_message (`&$msg_selects`, `&$msg_tables`, `&$msg_parameters`)
- integrate\_display\_buttons (`&$context['normal_buttons']`)
- integrate\_mod\_buttons (`&$context['mod_buttons']`)
- integrate\_prepare\_display\_context (`&$output`, `&$message`, `$counter`)

#### Sources/Errors.php
- integrate\_error\_types (`&$other_error_types`, `&$error_type`, `$error_message`, `$file`, `$line`)
- integrate\_output\_error (`$message`, `$error_type`, `$error_level`, `$file`, `$line`)

#### Sources/Groups.php
- integrate\_manage\_groups (`&$subActions`)

#### Sources/Help.php
- integrate\_manage\_help (`&$subActions`)
- integrate\_helpadmin

#### Sources/Likes.php
- integrate\_valid\_likes (`$this->_type`, `$this->_content`, `$this->_sa`, `$this->_js`, `$this->_extra`)
- integrate\_issue\_like\_before (`&$type`, `&$content`, `&$user`, `&$time`)
- integrate\_issue\_like (`$this`)
- integrate\_likes\_json\_response (`&$print`)

#### Sources/Load.php
- integrate\_load\_average (`$modSettings['load_average']`)
- integrate\_pre\_load
- integrate\_verify\_user
- integrate\_verify\_tfa (`$id_member`, `$user_settings`)
- integrate\_user\_info
- integrate\_load\_member\_data (`&$select_columns`, `&$select_tables`, `&$set`)
- integrate\_member\_context (`&$memberContext[$user]`, `$user`, `$display_custom_fields`)
- integrate\_pre\_load\_theme (`&$id_theme`)
- integrate\_simple\_actions (`&$simpleActions`, `&$simpleAreas`, `&$simpleSubActions`, `&$extraParams`, `&$xmlActions`)
- integrate\_load\_theme
- pre\_cache\_quick\_get (`&$key`, `&$file`, `&$function`, `&$params`, `&$level`)
- post\_cache\_quick\_get (`&$cache_block`)
- cache\_put\_data (`&$key`, `&$value`, `&$ttl`)
- cache\_get\_data (`&$key`, `&$ttl`, `&$value`)
- integrate\_clean\_cache
- integrate\_set\_avatar\_data (`&$image`, `&$data`)

#### Sources/Logging.php
- integrate\_log\_types (`&$log_types`)

#### Sources/LogInOut.php
- integrate\_validate\_login (`$_POST['user']`, `isset($_POST['passwrd']) ? $_POST['passwrd'] : null`, `$modSettings['cookieTime']`, `true`)
- integrate\_other\_passwords (`&$other_passwords`)
- integrate\_login (`$user_settings['member_name']`, `null`, `$modSettings['cookieTime']`)
- integrate\_logout (`$user_settings['member_name']`)

#### Sources/ManageAttachments.php
- integrate\_manage\_attachments (`&$subActions`)
- integrate\_modify\_attachment\_settings (`&$config_vars`)
- integrate\_save\_attachment\_settings
- integrate\_modify\_avatar\_settings (`&$config_vars`)
- integrate\_save\_avatar\_settings
- integrate\_attachments\_browse (`&$listOptions`, `&$titles`, `&$list_title`)
- integrate\_attachment\_remove (`&$filesRemoved`, `$attachments`)
- integrate\_remove\_attachments (`$attach`)
- integrate\_repair\_attachments\_nomsg (`&$ignore_ids`, `$_GET['substep']`, `$_GET['substep'] + 500`)
- integrate\_approve\_attachments (`$attachments`)

#### Sources/ManageBans.php
- integrate\_manage\_bans (`&$subActions`)
- integrate\_load\_addtional\_ip\_ban (`&$search_list`)

#### Sources/ManageBoards.php
- integrate\_manage\_boards (`&$subActions`)
- integrate\_boards\_main
- integrate\_edit\_category
- integrate\_edit\_board
- integrate\_modify\_board\_settings (`&$config_vars`)
- integrate\_save\_board\_settings

#### Sources/ManageCalendar.php
- integrate\_manage\_calendar (`&$subActions`)
- integrate\_modify\_calendar\_settings (`&$config_vars`)
- integrate\_save\_calendar\_settings

#### Sources/ManageLanguages.php
- integrate\_manage\_languages (`&$subActions`)
- integrate\_language\_settings (`&$config_vars`)
- integrate\_save\_language\_settings (`&$config_vars`)
- integrate\_modifylanguages (`&$themes`, `&$lang_dirs`, `&$allows_add_remove`, `&$additional_string_types`)
- integrate\_language\_edit\_helptext (`&$special_groups`)

#### Sources/ManageMail.php
- integrate\_manage\_mail (`&$subActions`)
- integrate\_modify\_mail\_settings (`&$config_vars`)
- integrate\_save\_mail\_settings

#### Sources/ManageMaintenance.php
- integrate\_manage\_maintenance (`&$subActions`)
- integrate\_convert\_msgbody (`$body_type`)

#### Sources/ManageMembergroups.php
- integrate\_manage\_membergroups (`&$subActions`)
- integrate\_pre\_add\_membergroup
- integrate\_add\_membergroup (`$id_group`, `$postCountBasedGroup`)
- integrate\_save\_membergroup (`(int $_REQUEST['group']`)
- integrate\_view\_membergroup
- integrate\_modify\_membergroup\_settings (`&$config_vars`)
- integrate\_save\_membergroup\_settings

#### Sources/ManageMembers.php
- integrate\_manage\_members (`&$subActions`)
- integrate\_view\_members\_params (`&$params`)
- integrate\_activate (`$member['username']`)

#### Sources/ManageNews.php
- integrate\_manage\_news (`&$subActions`)
- integrate\_modify\_news\_settings (`&$config_vars`)
- integrate\_save\_news\_settings

#### Sources/ManagePaid.php
- integrate\_manage\_subscriptions (`&$subActions`)
- integrate\_delete\_subscription (`$context['sub_id']`)
- integrate\_save\_subscription (`($context['action_type'] == 'add' ? $id_subscribe : $context['sub_id'])`, `$_POST['name']`, `$_POST['desc']`, `$isActive`, `$span`, `$cost`, `$_POST['prim_group']`, `$addgroups`, `$isRepeatable`, `$allowpartial`, `$emailComplete`, `$reminder`)

#### Sources/ManagePermissions.php
- integrate\_manage\_permissions (`&$subActions`)
- integrate\_modify\_permission\_settings (`&$config_vars`)
- integrate\_save\_permission\_settings
- integrate\_load\_permission\_levels (`&$groupLevels`, `&$boardLevels`)
- integrate\_load\_permissions (`&$permissionGroups`, `&$permissionList`, `&$leftPermissionGroups`, `&$hiddenPermissions`, `&$relabelPermissions`)
- integrate\_load\_illegal\_permissions
- integrate\_load\_illegal\_guest\_permissions
- integrate\_post\_moderation\_mapping (`&$mappings`)

#### Sources/ManagePosts.php
- integrate\_manage\_posts (`&$subActions`)
- integrate\_save\_censors (`&$updates`)
- integrate\_censors
- integrate\_modify\_post\_settings (`&$config_vars`)
- integrate\_save\_post\_settings
- integrate\_modify\_topic\_settings (`&$config_vars`)
- integrate\_save\_topic\_settings

#### Sources/ManageRegistration.php
- integrate\_manage\_registrations (`&$subActions`)
- integrate\_modify\_registration\_settings (`&$config_vars`)
- integrate\_save\_registration\_settings

#### Sources/ManageScheduledTasks.php
- integrate\_manage\_scheduled\_tasks (`&$subActions`)
- integrate\_scheduled\_tasks\_settings (`&$config_vars`)
- integrate\_save\_scheduled\_tasks\_settings (`&$save_vars`)

#### Sources/ManageSearch.php
- integrate\_manage\_search (`&$subActions`)
- integrate\_modify\_search\_settings (`&$config_vars`)
- integrate\_save\_search\_settings
- integrate\_modify\_search\_weights (`&$factors`)
- integrate\_save\_search\_weights

#### Sources/ManageSearchEngines.php
- integrate\_manage\_search\_engines (`&$subActions`)
- integrate\_modify\_search\_engine\_settings (`&$config_vars`)
- integrate\_save\_search\_engine\_settings

#### Sources/ManageServer.php
- integrate\_server\_settings (`&$subActions`)
- integrate\_general\_settings (`&$config_vars`)
- integrate\_save\_general\_settings
- integrate\_database\_settings (`&$config_vars`)
- integrate\_save\_database\_settings
- integrate\_cookie\_settings (`&$config_vars`)
- integrate\_save\_cookie\_settings
- integrate\_general\_security\_settings (`&$config_vars`)
- integrate\_save\_general\_security\_settings
- integrate\_modify\_cache\_settings (`&$config_vars`)
- integrate\_save\_cache\_settings
- integrate\_loadavg\_settings (`&$config_vars`)
- integrate\_save\_loadavg\_settings
- integrate\_prepare\_db\_settings (`&$config_vars`)

#### Sources/ManageSettings.php
- integrate\_modify\_features (`&$subActions`)
- integrate\_modify\_modifications (`&$subActions`)
- integrate\_modify\_basic\_settings (`&$config_vars`)
- integrate\_save\_basic\_settings
- integrate\_modify\_bbc\_settings (`&$config_vars`)
- integrate\_save\_bbc\_settings (`$bbcTags`)
- integrate\_layout\_settings (`&$config_vars`)
- integrate\_save\_layout\_settings
- integrate\_likes\_settings (`&$config_vars`)
- integrate\_save\_likes\_settings
- integrate\_mentions\_settings (`&$config_vars`)
- integrate\_save\_mentions\_settings
- integrate\_warning\_settings (`&$config_vars`)
- integrate\_save\_warning\_settings (`&$save_vars`)
- integrate\_spam\_settings (`&$config_vars`)
- integrate\_save\_spam\_settings (`&$save_vars`)
- integrate\_signature\_settings (`&$config_vars`)
- integrate\_apply\_signature\_settings (`&$sig`, `$sig_limits`, `$disabledTags`)
- integrate\_save\_signature\_settings (`&$sig_limits`, `&$bbcTags`)
- integrate\_prune\_settings (`&$config_vars`, `&$prune_toggle`, `false`)
- integrate\_prune\_settings (`&$savevar`, `&$prune_toggle`, `true`)
- integrate\_general\_mod\_settings (`&$config_vars`)
- integrate\_save\_general\_mod\_settings (`&$save_vars`)

#### Sources/ManageSmileys.php
- integrate\_manage\_smileys (`&$subActions`)
- integrate\_modify\_smiley\_settings (`&$config_vars`)
- integrate\_save\_smiley\_settings

#### Sources/Memberlist.php
- integrate\_memberlist\_buttons

#### Sources/MessageIndex.php
- integrate\_pre\_messageindex (`&$sort_methods`, `&$sort_methods_table`)
- integrate\_message\_index (`&$message_index_selects`, `&$message_index_tables`, `&$message_index_parameters`, `&$message_index_wheres`, `&$topic_ids`)
- integrate\_quick\_mod\_actions
- integrate\_messageindex\_buttons (`&$context['normal_buttons']`)

#### Sources/ModerationCenter.php
- integrate\_mod\_centre\_blocks (`&$valid_blocks`)
- integrate\_warning\_log\_actions (`&$subActions`)

#### Sources/Modlog.php
- integrate\_viewModLog (`&$listOptions`, `&$moderation_menu_name`)

#### Sources/MoveTopic.php
- integrate\_movetopic2\_end

#### Sources/News.php
- integrate\_xmlfeeds (`&$subActions`)
- integrate\_xml\_data (`&$xml_data`, `&$feed_meta`, `&$namespaces`, `&$extraFeedTags`, `&$forceCdataKeys`, `&$nsKeys`, `$xml_format`, `$_GET['sa']`)
- integrate\_fix\_url (`&$val`)

#### Sources/PackageGet.php
- integrate\_package\_get (`&$subActions`)
- integrate\_package\_download
- integrate\_package\_upload

#### Sources/Packages.php
- integrate\_manage\_packages (`&$subActions`)
- integrate\_modification\_types
- integrate\_packages\_sort\_id (`&$sort_id`, `&$packages`)

#### Sources/PersonalMessage.php
- integrate\_conversation\_buttons
- integrate\_prepare\_pm\_context (`&$output`, `&$message`, `$counter`)
- integrate\_search\_pm\_context
- integrate\_pm\_post
- integrate\_pm\_error

#### Sources/Poll.php
- integrate\_poll\_vote (`&$row['id_poll']`, `&$pollOptions`)
- integrate\_poll\_add\_edit (`$bcinfo['id_poll']`, `$isEdit`)
- integrate\_poll\_remove (`$pollID`)

#### Sources/Post.php
- integrate\_post\_start
- integrate\_post\_errors (`&$post_errors`, `&$minor_errors`)
- integrate\_post\_end
- integrate\_post2\_start
- integrate\_poll\_add\_edit (`$id_poll`, `false`)
- integrate\_post2\_end

#### Sources/PostModeration.php
- integrate\_post\_moderation (`&$subActions`)

#### Sources/Profile-Actions.php
- integrate\_activate (`$user_profile[$memID]['member_name']`)

#### Sources/Profile-Modify.php
- integrate\_reset\_pass (`$cur_profile['member_name']`, `$value`, `$_POST['passwrd1']`)
- integrate\_load\_profile\_fields (`&$profile_fields`)
- integrate\_setup\_profile\_context (`&$fields`)
- integrate\_save\_custom\_profile\_fields (`&$changes`, `&$log_changes`, `&$errors`, `$returnErrors`, `$memID`, `$area`, `$sanitize`, `&$deletes`)
- integrate\_remove\_buddy (`$memID`)
- integrate\_add\_buddies (`$memID`, `&$new_buddies`)
- integrate\_view\_buddies (`$memID`)
- integrate\_theme\_options
- integrate\_alert\_types (`&$alert_types`, `&$group_options`)
- integrate\_profile\_profileSaveGroups (`$value`, `$additional_groups`)

#### Sources/Profile-View.php
- integrate\_fetch\_alerts (`&$alerts`)
- integrate\_show\_alert (`&$alert`, `&$link`)
- integrate\_profile\_showPosts
- integrate\_profile\_stats (`$memID`, `&$context['text_stats']`)
- integrate\_profile\_trackip (`$ip_string`, `$ip_var`)

#### Sources/Profile.php
- integrate\_pre\_profile\_areas (`&$profile_areas`)
- integrate\_verify\_password (`$cur_profile['member_name']`, `$password`, `false`, `true`)
- integrate\_profile\_save (`&$profile_vars`, `&$post_errors`, `$memID`, `$cur_profile`, `$current_area`)
- integrate\_reset\_pass (`$cur_profile['member_name']`, `$cur_profile['member_name']`, `$_POST['passwrd2']`)
- integrate\_profile\_popup (`&$profile_items`)
- integrate\_load\_custom\_profile\_fields (`$memID`, `$area`)

#### Sources/Recent.php
- integrate\_recent\_RecentPosts
- integrate\_recent\_buttons
- integrate\_unread\_list

#### Sources/Register.php
- integrate\_activate (`$regOptions['username']`)
- integrate\_activate (`$row['member_name']`)

#### Sources/Reminder.php
- integrate\_reset\_pass (`$username`, `$username`, `$_POST['passwrd1']`)
- integrate\_reset\_pass (`$row['member_name']`, `$row['member_name']`, `$_POST['passwrd1']`)

#### Sources/RemoveTopic.php
- integrate\_remove\_topics (`$topics`)
- integrate\_remove\_message (`$message`)

#### Sources/Reports.php
- integrate\_report\_types
- integrate\_report\_buttons
- integrate\_reports\_boardperm (`&$disabled_permissions`)
- integrate\_reports\_groupperm (`&$disabled_permissions`)

#### Sources/Search.php
- integrate\_search
- integrate\_search\_weights (`&$weight_factors`)
- integrate\_search\_sort\_columns (`&$sort_columns`)
- integrate\_search\_params (`&$search_params`)
- integrate\_search\_blacklisted\_words (`&$blacklisted_words`)
- integrate\_search\_errors
- integrate\_subject\_only\_search\_query (`&$subject_query`, `&$subject_query_params`)
- integrate\_subject\_search\_query (`&$subject_query`)
- integrate\_main\_search\_query (`&$main_query`)
- integrate\_search\_message\_list (`&$msg_list`, `&$posters`)
- integrate\_quick\_mod\_actions\_search
- integrate\_search\_message\_context (`&$output`, `&$message`, `$counter`)

#### Sources/Security.php
- integrate\_validateSession (`&$types`)
- integrate\_verify\_password (`$user_info['username']`, `$_POST[$type . '_pass']`, `false`, `true`)
- integrate\_post\_ban\_permissions (`&$denied_permissions`)
- integrate\_warn\_permissions (`&$permission_change`)
- integrate\_heavy\_permissions\_session (`&$heavy_permissions`)
- integrate\_spam\_protection (`&$timeOverrides`)

#### Sources/Session.php
- integrate\_session\_handlers

#### Sources/ShowAttachments.php
- integrate\_pre\_download\_request
- integrate\_download\_request (`&$attachRequest`)

#### Sources/SplitTopics.php
- integrate\_split\_topic (`$split1`, `$split2`, `$new_subject`, `$id_board`)
- integrate\_merge\_topic (`$merged_topic`, `$updated_topics`, `$deleted_topics`, `$deleted_polls`)

#### Sources/Stats.php
- integrate\_forum\_stats

#### Sources/Subs-Attachments.php
- integrate\_attachment\_upload
- integrate\_createAttachment (`&$attachmentOptions`, `&$attachmentInserts`)
- integrate\_assign\_attachments (`&$attachIDs`, `&$msgID`)
- integrate\_pre\_parseAttachBBC (`$attachID`, `$msgID`)
- integrate\_post\_parseAttachBBC (`&$attachContext`)

#### Sources/Subs-Auth.php
- integrate\_cookie\_data (`$data`, `&$custom_data`)
- integrate\_validateSession (`&$types`)
- integrate\_reset\_pass (`$old_user`, `$user`, `$newPassword`)
- integrate\_mod\_cache
- integrate\_cookie (`$name`, `$value`, `$expire`, `$path`, `$domain`, `$secure`, `$httponly`)

#### Sources/Subs-BoardIndex.php
- integrate\_getboardtree (`$boardIndexOptions`, `&$categories`)
- integrate\_getboardtree (`$boardIndexOptions`, `&$this_category`)

#### Sources/Subs-Boards.php
- integrate\_pre\_modify\_board (`$id`, `&$boardOptions`)
- integrate\_modify\_board (`$id`, `$boardOptions`, `&$boardUpdates`, `&$boardUpdateParameters`)
- integrate\_create\_board (`&$boardOptions`, `&$board_columns`, `&$board_parameters`)
- integrate\_delete\_board (`$boards_to_remove`, `&$moveChildrenTo`)
- integrate\_pre\_boardtree (`&$boardColumns`, `&$boardParameters`, `&$boardJoins`, `&$boardWhere`, `&$boardOrder`)
- integrate\_boardtree\_board (`$row`)

#### Sources/Subs-Calendar.php
- integrate\_create\_event (`&$eventOptions`, `&$event_columns`, `&$event_parameters`)
- integrate\_modify\_event (`$event_id`, `&$eventOptions`, `&$event_columns`, `&$event_parameters`)
- integrate\_remove\_event (`$event_id`)

#### Sources/Subs-Categories.php
- integrate\_pre\_modify\_category (`$cat_id`, `&$catOptions`)
- integrate\_modify\_category (`$cat_id`, `&$catUpdates`, `&$catParameters`)
- integrate\_create\_category (`&$catOptions`, `&$cat_columns`, `&$cat_parameters`)
- integrate\_delete\_category (`$categories`, `&$moveBoardsTo`)

#### Sources/Subs-Editor.php
- integrate\_load\_message\_icons (`&$icons`)
- integrate\_bbc\_buttons (`&$context['bbc_tags']`, `&$editor_tag_map`)
- integrate\_sceditor\_options (`&$sce_options`)
- integrate\_autosuggest (`&$searchTypes`)

#### Sources/Subs-Membergroups.php
- integrate\_delete\_membergroups (`$groups`)
- integrate\_add\_members\_to\_group (`$members`, `$group`, `&$group_names`)

#### Sources/Subs-Members.php
- integrate\_delete\_members (`$users`)
- integrate\_register\_check (`&$regOptions`, `&$reg_errors`)
- integrate\_register (`&$regOptions`, `&$theme_vars`, `&$knownInts`, `&$knownFloats`)
- integrate\_post\_register (`&$regOptions`, `&$theme_vars`, `&$memberID`)
- integrate\_register\_after (`$regOptions`, `$memberID`)
- integrate\_reattribute\_posts (`$memID`, `$email`, `$membername`, `$post_count`, `&$updated`)

#### Sources/Subs-Post.php
- integrate\_outgoing\_email (`&$subject`, `&$message`, `&$headers`, `&$to_array`, `true`)
- integrate\_personal\_message (`&$recipients`, `&$from`, `&$subject`, `&$message`)
- integrate\_personal\_message\_after (`&$id_pm`, `&$log`, `&$recipients`, `&$from`, `&$subject`, `&$message`)
- integrate\_create\_post (`&$msgOptions`, `&$topicOptions`, `&$posterOptions`, `&$message_columns`, `&$message_parameters`)
- integrate\_after\_create\_post (`$msgOptions`, `$topicOptions`, `$posterOptions`, `$message_columns`, `$message_parameters`)
- integrate\_before\_create\_topic (`&$msgOptions`, `&$topicOptions`, `&$posterOptions`, `&$topic_columns`, `&$topic_parameters`)
- integrate\_create\_topic (`&$msgOptions`, `&$topicOptions`, `&$posterOptions`)
- integrate\_modify\_topic (`&$topics_columns`, `&$update_parameters`, `&$msgOptions`, `&$topicOptions`, `&$posterOptions`)
- integrate\_modify\_post (`&$messages_columns`, `&$update_parameters`, `&$msgOptions`, `&$topicOptions`, `&$posterOptions`, `&$messageInts`)

#### Sources/Subs-Themes.php
- integrate\_get\_single\_theme (`&$themeValues`, `$id`)
- integrate\_get\_all\_themes (`&$themeValues`, `$enable_only`)
- integrate\_get\_installed\_themes (`&$themeValues`)
- integrate\_theme\_install (`&$context['to_install']`, `$id_theme`)

#### Sources/Subs.php
- integrate\_change\_member\_data (`$member_names`, `$var`, `&$data[$var]`, `&$knownInts`, `&$knownFloats`)
- integrate\_pre\_parsebbc (`&$message`, `&$smileys`, `&$cache_id`, `&$parse_tags`)
- integrate\_bbc\_codes (`&$codes`, `&$no_autolink_tags`)
- integrate\_bbc\_print (`&$disabled`)
- integrate\_post\_parsebbc (`&$message`, `&$smileys`, `&$cache_id`, `&$parse_tags`)
- integrate\_smileys (`&$smileyPregSearch`, `&$smileyPregReplacements`)
- integrate\_proxy (`$url`, `&$proxied_url`)
- integrate\_redirect (`&$setLocation`, `&$refresh`, `&$permanent`)
- integrate\_exit (`$do_footer`)
- integrate\_theme\_context
- integrate\_security\_files (`&$securityFiles`)
- integrate\_pre\_javascript\_output (`&$do_deferred`)
- integrate\_pre\_css\_output
- integrate\_menu\_buttons (`&$buttons`)
- integrate\_current\_action (`&$current_action`)

#### Sources/Themes.php
- integrate\_manage\_themes (`&$subActions`)
- integrate\_theme\_options
- integrate\_theme\_settings
- integrate\_wrap\_action

#### Sources/ViewQuery.php
- integrate\_egg\_nog

#### Sources/Who.php
- who\_allowed (`&$allowedActions`)
- integrate\_whos\_online (`$actions > 0`)
- whos\_online\_after (`&$urls`, `&$data`)
- integrate\_credits

#### Sources/Xml.php
- integrate\_XMLhttpMain\_subActions (`&$subActions`)

#### Sources/tasks/Likes-Notify.php
- integrate\_find\_like\_author (`$this->_details['content_type']`, `$this->_details['content_id']`)

#### Themes/default/Post.template.php
- integrate\_upload\_template