# omarbot
omarbot.php
<?php

ob_start();
$API_KEY = '6017332730:AAE2Gh-5wCdZwy8xjyKadhM4oJnEwWVX6m0'; /* توكن البوت*/
define('API_KEY',$API_KEY);
function bot($method,$webhook=[]){
$webhook = http_build_query($webhook);
$url ="https://api.telegram.org/bot".API_KEY."/".$method."?$webhook";
$webhook = file_get_contents($url);
return json_decode($webhook);}
$update = json_decode(file_get_contents('php://input'));
$message = $update->message;
$chat_id = $message->chat->id;
$text = $message->text;
$chat_id2 = $update->callback_query->message->chat->id;
$message_id = $update->callback_query->message->message_id;
$data = $update->callback_query->data;
$name = $update->callback_query->from->first_name;
$namee = $update->callback_query->from->last_name;
$update = json_decode(file_get_contents("php://input"));
$message = $update->message;
$txt = $message->caption;
$text = $message->text;
$chat_id = $message->chat->id;
$from_id = $message->from->id;
$new = $message->new_chat_members;
$message_id = $message->message_id;
$type = $message->chat->type;
$name = $message->from->first_name;
if(isset($update->callback_query)){
$up = $update->callback_query;
$chat_id = $up->message->chat->id;
$from_id = $up->from->id;
$user = $up->from->username;
$name = $up->from->first_name;
$namee = $up->from->last_name;
$message_id = $up->message->message_id;
$data = $up->data;
}
if($text == '/start'){
bot('sendMessage',[
'chat_id'=>$chat_id,
'text'=>"
*❍ Hello dear user  in the best translation bot ever You can translate into 107 languages .*
*❍ After each translation, send /start to reactivate the bot .*
*❍ The bot was programmed by :* [omar](tg://user?id=1036195630) .
*❍ The copy price is $25 if you want to buy .*
*❍ If the bot does not translate, shorten the sentence.*",
'parse_mode' =>"markdown",
'disable_web_page_preview' => true,
'reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>'GO' ,'callback_data'=>"start1"]],
]
])
]);
}
if($data=="home"){
bot('sendMessage',[
'chat_id'=>$chat_id,
'text'=>"
*❍ Hello dear user  in the best translation bot ever You can translate into 107 languages .*
*❍ After each translation, send /start to reactivate the bot .*
*❍ The bot was programmed by :* [omar](tg://user?id=1036195630) .
*❍ The copy price is $25 if you want to buy .*
*❍ If the bot does not translate, shorten the sentence.*",
'parse_mode' =>"markdown",
'disable_web_page_preview' => true,
'reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>'GO' ,'callback_data'=>"start1"]],
]
])
]);
}

if($data=="start1"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"*❍ Choose the language of translation : 1 .* ",
'parse_mode' =>"markdown",
'disable_web_page_preview' => true,
'reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>'Afrikaans' ,'callback_data'=>"Afrikaans"],['text'=>'Albanian' ,'callback_data'=>"Albanian"],['text'=>'Amharic' ,'callback_data'=>"Amharic"]],
[['text'=>'Arabic' ,'callback_data'=>"Arabic"],['text'=>'Armenian' ,'callback_data'=>"Armenian"]],
[['text'=>'Azerbaijani' ,'callback_data'=>"Azerbaijani"]],
[['text'=>'Basque' ,'callback_data'=>"Basque"],['text'=>'Belarusian' ,'callback_data'=>"Belarusian"]],
[['text'=>'Bengali' ,'callback_data'=>"Bengali"],['text'=>'Bosnian' ,'callback_data'=>"Bosnian"],['text'=>'Bulgarian' ,'callback_data'=>"Bulgarian"]],
[['text'=>'Catalan' ,'callback_data'=>"Catalan"],['text'=>'Chinese (Simplified)' ,'callback_data'=>"Chinese (Simplified)"]],
[['text'=>'Chinese (Traditional)' ,'callback_data'=>"Chinese (Traditional)"]],
[['text'=>'Corsican' ,'callback_data'=>"Corsican"],['text'=>'Croatian' ,'callback_data'=>"Croatian"]],
[['text'=>'Czech' ,'callback_data'=>"Czech"],['text'=>'Danish' ,'callback_data'=>"Danish"],['text'=>'Dutch' ,'callback_data'=>"Dutch"]],
[['text'=>'English' ,'callback_data'=>"English"],['text'=>'Esperanto' ,'callback_data'=>"Esperanto"]],
[['text'=>'Estonian' ,'callback_data'=>"Estonian"]],
[['text'=>'2' ,'callback_data'=>"start2"],['text'=>'HOME' ,'callback_data'=>"home"]],
]
])
]);
}

if($data=="start2"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"* ❍ Choose the language of translation : 2 .*",
'parse_mode' =>"markdown",
'disable_web_page_preview' => true,
'reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>'Finnish' ,'callback_data'=>"Finnish"]],
[['text'=>'French' ,'callback_data'=>"French"],['text'=>'Frisian' ,'callback_data'=>"Frisian"]],
[['text'=>'Galician' ,'callback_data'=>"Galician"],['text'=>'Georgian' ,'callback_data'=>"Georgian"],['text'=>'German' ,'callback_data'=>"German"]],
[['text'=>'Greek' ,'callback_data'=>"Greek"],['text'=>'Gujarati' ,'callback_data'=>"Gujarati"]],
[['text'=>'Haitian Creole' ,'callback_data'=>"Haitian Creole"]],
[['text'=>'Hausa' ,'callback_data'=>"Hausa"],['text'=>'Hawaiian' ,'callback_data'=>"Hawaiian"]],
[['text'=>'Hebrew' ,'callback_data'=>"Hebrew"],['text'=>'Hindi' ,'callback_data'=>"Hindi"],['text'=>'Hungarian' ,'callback_data'=>"Hungarian"]],
[['text'=>'Icelandic' ,'callback_data'=>"Icelandic"],['text'=>'Interlingua' ,'callback_data'=>"Interlingua"]],
[['text'=>'Igbo' ,'callback_data'=>"Igbo"]],
[['text'=>'Indonesian' ,'callback_data'=>"Indonesian"],['text'=>'Irish' ,'callback_data'=>"Irish"]],
[['text'=>'Italian' ,'callback_data'=>"Italian"],['text'=>'Japanese' ,'callback_data'=>"Japanese"],['text'=>'Javanese' ,'callback_data'=>"Javanese"]],
[['text'=>'Kannada' ,'callback_data'=>"Kannada"],['text'=>'Kazakh' ,'callback_data'=>"Kazakh"]],
[['text'=>'Khmer' ,'callback_data'=>"Khmer"]],
[['text'=>'1' ,'callback_data'=>"start1"],['text'=>'3' ,'callback_data'=>"start3"]],
]
])
]);
}

if($data=="start3"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"*❍ Choose the language of translation : 3 .*",
'parse_mode' =>"markdown",
'disable_web_page_preview' => true,
'reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>'Korean' ,'callback_data'=>"Korean"],['text'=>'Kurdish' ,'callback_data'=>"Kurdish"],['text'=>'Kyrgyz' ,'callback_data'=>"Kyrgyz"]],
[['text'=>'Lao' ,'callback_data'=>"Lao"],['text'=>'Latin' ,'callback_data'=>"Latin"]],
[['text'=>'Latvian' ,'callback_data'=>"Latvian"]],
[['text'=>'Lithuanian' ,'callback_data'=>"Lithuanian"],['text'=>'Luxembourgish' ,'callback_data'=>"Luxembourgish"]],
[['text'=>'Macedonian' ,'callback_data'=>"Macedonian"],['text'=>'Malagasy' ,'callback_data'=>"Malagasy"],['text'=>'Malay' ,'callback_data'=>"Malay"]],
[['text'=>'Malayalam' ,'callback_data'=>"Malayalam"],['text'=>'Maltese' ,'callback_data'=>"Maltese"]],
[['text'=>'Maori' ,'callback_data'=>"Maori"]],
[['text'=>'Marathi' ,'callback_data'=>"Marathi"],['text'=>'Mongolian' ,'callback_data'=>"Mongolian"]],
[['text'=>'Myanmar (Burmese)' ,'callback_data'=>"Myanmar (Burmese)"],['text'=>'Nepali' ,'callback_data'=>"Nepali"],['text'=>'Norwegian' ,'callback_data'=>"Norwegian"]],
[['text'=>'Nyanja (Chichewa)' ,'callback_data'=>"Nyanja (Chichewa)"],['text'=>'Odia (Oriya)' ,'callback_data'=>"Odia (Oriya)"]],
[['text'=>'Pashto' ,'callback_data'=>"Pashto"]],
[['text'=>'Persian' ,'callback_data'=>"Persian"],['text'=>'Polish' ,'callback_data'=>"Polish"]],
[['text'=>'Portuguese (Portugal, Brazil)' ,'callback_data'=>"Portuguese (Portugal, Brazil)"],['text'=>'Punjabi' ,'callback_data'=>"Punjabi"],['text'=>'Romanian' ,'callback_data'=>"Romanian"]],
[['text'=>'Russian' ,'callback_data'=>"Russian"],['text'=>'Samoan' ,'callback_data'=>"Samoan"]],
[['text'=>'Scots Gaelic' ,'callback_data'=>"Scots Gaelic"]],
[['text'=>'Serbian' ,'callback_data'=>"Serbian"],['text'=>'Sesotho' ,'callback_data'=>"Sesotho"]],
[['text'=>'Shona' ,'callback_data'=>"Shona"],['text'=>'Sindhi' ,'callback_data'=>"Sindhi"],['text'=>'Sinhala (Sinhalese)' ,'callback_data'=>"Sinhala (Sinhalese)"]],
[['text'=>'Slovak' ,'callback_data'=>"Slovak"]],
[['text'=>'Slovenian' ,'callback_data'=>"Slovenian"],['text'=>'Somali' ,'callback_data'=>"Somali"]],
[['text'=>'Spanish' ,'callback_data'=>"Spanish"],['text'=>'Sundanese' ,'callback_data'=>"Sundanese"],['text'=>'Swahili' ,'callback_data'=>"Swahili"]],
[['text'=>'Swedish' ,'callback_data'=>"Swedish"],['text'=>'Tagalog (Filipino)' ,'callback_data'=>"Tagalog (Filipino)"]],
[['text'=>'Tajik' ,'callback_data'=>"Tajik"]],
[['text'=>'2' ,'callback_data'=>"start2"],['text'=>'4' ,'callback_data'=>"start4"]],
]
])
]);
}

if($data=="start4"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"*❍ Choose the language of translation : 4 .*",
'parse_mode' =>"markdown",
'disable_web_page_preview' => true,
'reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>'Tamil' ,'callback_data'=>"Tamil"]],
[['text'=>'Tatar' ,'callback_data'=>"Tatar"],['text'=>'Telugu' ,'callback_data'=>"Telugu"]],
[['text'=>'Thai' ,'callback_data'=>"Thai"],['text'=>'Turkish' ,'callback_data'=>"Turkish"],['text'=>'Turkmen' ,'callback_data'=>"Turkmen"]],
[['text'=>'Ukrainian' ,'callback_data'=>"Ukrainian"],['text'=>'Urdu' ,'callback_data'=>"Urdu"]],
[['text'=>'Uyghur' ,'callback_data'=>"Uyghur"]],
[['text'=>'Uzbek' ,'callback_data'=>"Uzbek"],['text'=>'Vietnamese' ,'callback_data'=>"Vietnamese"]],
[['text'=>'Welsh' ,'callback_data'=>"Welsh"],['text'=>'Xhosa' ,'callback_data'=>"Xhosa"],['text'=>'Yiddish' ,'callback_data'=>"Yiddish"]],
[['text'=>'Yoruba' ,'callback_data'=>"Yoruba"],['text'=>'Zulu' ,'callback_data'=>"Zulu"]],
[['text'=>'3' ,'callback_data'=>"start3"]],
]
])
]);
}
mkdir("chat_id");
mkdir("chat_id/$chat_id");
$get_trgma=file_get_contents('chat_id/'.$chat_id.'/trgm.txt');
if($data=="Afrikaans"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Afrikaans",
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Afrikaans");
}
if ($text != "/start" and $get_trgma=="Afrikaans"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=af&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>" `$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Albanian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Albanian",
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Albanian");
}
if ($text != "/start" and $get_trgma=="Albanian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=sq&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Amharic"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Amharic",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Amharic");
}
if ($text != "/start" and $get_trgma=="Amharic"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=am&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Arabic"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Arabic",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Arabic");
}
if ($text != "/start" and $get_trgma=="Arabic"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ar&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Armenian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Armenian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Armenian");
}
if ($text != "/start" and $get_trgma=="Armenian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=hy&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Azerbaijani"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Azerbaijani",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Azerbaijani");
}
if ($text != "/start" and $get_trgma=="Azerbaijani"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=az&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Basque"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Basque",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Basque");
}
if ($text != "/start" and $get_trgma=="Basque"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=eu&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Belarusian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Belarusian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Belarusian");
}
if ($text != "/start" and $get_trgma=="Belarusian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=be&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Bengali"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Bengali",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Bengali");
}
if ($text != "/start" and $get_trgma=="Bengali"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=bn&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Bosnian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Bosnian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Bosnian");
}
if ($text != "/start" and $get_trgma=="Bosnian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=bs&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}if($data=="Bulgarian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Bulgarian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Bulgarian");
}
if ($text != "/start" and $get_trgma=="Bulgarian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=bg&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Catalan"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Catalan",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Catalan");
}
if ($text != "/start" and $get_trgma=="Catalan"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ca&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Chinese (Simplified)"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Chinese (Simplified)",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Chinese (Simplified)");
}
if ($text != "/start" and $get_trgma=="Chinese (Simplified)"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=zh&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Chinese (Traditional)"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Chinese (Traditional)",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Chinese (Traditional)");
}
if ($text != "/start" and $get_trgma=="Chinese (Traditional)"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=zh_TW&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Corsican"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Corsican",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Corsican");
}
if ($text != "/start" and $get_trgma=="Corsican"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=co&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Croatian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Croatian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Croatian");
}
if ($text != "/start" and $get_trgma=="Croatian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=hr&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Czech"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Czech",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Czech");
}
if ($text != "/start" and $get_trgma=="Czech"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=cs&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Danish"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Danish",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Danish");
}
if ($text != "/start" and $get_trgma=="Danish"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=da&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Dutch"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Dutch",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Dutch");
}
if ($text != "/start" and $get_trgma=="Dutch"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=nl&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="English"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى English",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","English");
}
if ($text != "/start" and $get_trgma=="English"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=en&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}
if($data=="Esperanto"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Esperanto",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Esperanto");
}
if ($text != "/start" and $get_trgma=="Esperanto"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=eo&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Estonian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Estonian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Estonian");
}
if ($text != "/start" and $get_trgma=="Estonian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=et&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Finnish"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Finnish",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Finnish");
}
if ($text != "/start" and $get_trgma=="Finnish"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=fi&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="French"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى French",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","French");
}
if ($text != "/start" and $get_trgma=="French"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=fr&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Frisian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Frisian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Frisian");
}
if ($text != "/start" and $get_trgma=="Frisian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=fy&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Galician"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Galician",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Galician");
}
if ($text != "/start" and $get_trgma=="Galician"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=gl&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Georgian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Georgian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Georgian");
}
if ($text != "/start" and $get_trgma=="Georgian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ka&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="German"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى German",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","German");
}
if ($text != "/start" and $get_trgma=="German"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=de&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Greek"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Greek",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Greek");
}
if ($text != "/start" and $get_trgma=="Greek"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=el&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Gujarati"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Gujarati",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Gujarati");
}
if ($text != "/start" and $get_trgma=="Gujarati"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=gu&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}
if($data=="Haitian Creole"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Haitian Creole",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Haitian Creole");
}
if ($text != "/start" and $get_trgma=="Haitian Creole"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ht&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Hausa"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Hausa",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Hausa");
}
if ($text != "/start" and $get_trgma=="Hausa"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ha&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Hawaiian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Hawaiian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Hawaiian");
}
if ($text != "/start" and $get_trgma=="Hawaiian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=haw&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Hebrew"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Hebrew",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Hebrew");
}
if ($text != "/start" and $get_trgma=="Hebrew"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=he&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Hindi"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Hindi",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Hindi");
}
if ($text != "/start" and $get_trgma=="Hindi"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=hi&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Hungarian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Hungarian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Hungarian");
}
if ($text != "/start" and $get_trgma=="Hungarian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=hu&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Icelandic"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Icelandic",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Icelandic");
}
if ($text != "/start" and $get_trgma=="Icelandic"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=is&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Interlingua"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Interlingua",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Interlingua");
}
if ($text != "/start" and $get_trgma=="Interlingua"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ia&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Igbo"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Igbo",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Igbo");
}
if ($text != "/start" and $get_trgma=="Igbo"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ig&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Indonesian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Indonesian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Indonesian");
}
if ($text != "/start" and $get_trgma=="Indonesian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=id&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}
if($data=="Irish"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Irish",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Irish");
}
if ($text != "/start" and $get_trgma=="Irish"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ga&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Italian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Italian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Italian");
}
if ($text != "/start" and $get_trgma=="Italian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=it&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Japanese"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Japanese",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Japanese");
}
if ($text != "/start" and $get_trgma=="Japanese"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ja&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Javanese"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Javanese",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Javanese");
}
if ($text != "/start" and $get_trgma=="Javanese"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=jv&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Kannada"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Kannada",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Kannada");
}
if ($text != "/start" and $get_trgma=="Kannada"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=kn&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Kazakh"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Kazakh",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Kazakh");
}
if ($text != "/start" and $get_trgma=="Kazakh"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=kk&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Khmer"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Khmer",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Khmer");
}
if ($text != "/start" and $get_trgma=="Khmer"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=km&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Korean"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Korean",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Korean");
}
if ($text != "/start" and $get_trgma=="Korean"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ko&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Kurdish"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Kurdish",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Kurdish");
}
if ($text != "/start" and $get_trgma=="Kurdish"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ku&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Kyrgyz"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Kyrgyz",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Kyrgyz");
}
if ($text != "/start" and $get_trgma=="Kyrgyz"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ky&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}
if($data=="Lao"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Lao",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Lao");
}
if ($text != "/start" and $get_trgma=="Lao"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=lo&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Latin"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Latin",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Latin");
}
if ($text != "/start" and $get_trgma=="Latin"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=la&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Latvian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Latvian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Latvian");
}
if ($text != "/start" and $get_trgma=="Latvian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=lv&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Lithuanian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Lithuanian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Lithuanian");
}
if ($text != "/start" and $get_trgma=="Lithuanian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=lt&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Luxembourgish"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Luxembourgish",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Luxembourgish");
}
if ($text != "/start" and $get_trgma=="Luxembourgish"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=lb&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Macedonian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Macedonian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Macedonian");
}
if ($text != "/start" and $get_trgma=="Macedonian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=mk&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Malagasy"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Malagasy",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Malagasy");
}
if ($text != "/start" and $get_trgma=="Malagasy"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=mg&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Malay"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Malay",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Malay");
}
if ($text != "/start" and $get_trgma=="Malay"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ms&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Malayalam"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Malayalam",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Malayalam");
}
if ($text != "/start" and $get_trgma=="Malayalam"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ml&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Maltese"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Maltese",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Maltese");
}
if ($text != "/start" and $get_trgma=="Maltese"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=mt&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}
if($data=="Maori"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Maori",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Maori");
}
if ($text != "/start" and $get_trgma=="Maori"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=mi&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Marathi"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Marathi",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Marathi");
}
if ($text != "/start" and $get_trgma=="Marathi"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=mr&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Mongolian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Mongolian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Mongolian");
}
if ($text != "/start" and $get_trgma=="Mongolian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=mn&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Myanmar (Burmese)"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Myanmar (Burmese)",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Myanmar (Burmese)");
}
if ($text != "/start" and $get_trgma=="Myanmar (Burmese)"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=my&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Nepali"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Nepali",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Nepali");
}
if ($text != "/start" and $get_trgma=="Nepali"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ne&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Norwegian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Norwegian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","arTOru");
}
if ($text != "/start" and $get_trgma=="Norwegian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=no&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Nyanja (Chichewa)"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Nyanja (Chichewa)",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Nyanja (Chichewa)");
}
if ($text != "/start" and $get_trgma=="Nyanja (Chichewa)"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ny&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Odia (Oriya)"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Odia (Oriya)",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Odia (Oriya)");
}
if ($text != "/start" and $get_trgma=="Odia (Oriya)"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=or&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Pashto"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Pashto",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Pashto");
}
if ($text != "/start" and $get_trgma=="Pashto"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ps&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Persian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Persian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Persian");
}
if ($text != "/start" and $get_trgma=="Persian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=fa&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}
if($data=="Polish"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Polish",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Polish");
}
if ($text != "/start" and $get_trgma=="Polish"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=pl&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Portuguese (Portugal, Brazil)"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Portuguese (Portugal, Brazil)",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Portuguese (Portugal, Brazil)");
}
if ($text != "/start" and $get_trgma=="Portuguese (Portugal, Brazil)"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=pt&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Punjabi"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Punjabi",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Punjabi");
}
if ($text != "/start" and $get_trgma=="Punjabi"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=pa&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Romanian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Romanian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Romanian");
}
if ($text != "/start" and $get_trgma=="Romanian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ro&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Russian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Russian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Russian");
}
if ($text != "/start" and $get_trgma=="Russian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ru&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Samoan"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Samoan",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Samoan");
}
if ($text != "/start" and $get_trgma=="Samoan"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=sm&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Scots Gaelic"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Scots Gaelic",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Scots Gaelic");
}
if ($text != "/start" and $get_trgma=="Scots Gaelic"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=gd&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Serbian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Serbian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Serbian");
}
if ($text != "/start" and $get_trgma=="Serbian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=sr&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Sesotho"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Sesotho",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Sesotho");
}
if ($text != "/start" and $get_trgma=="Sesotho"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=st&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Shona"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Shona",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Shona");
}
if ($text != "/start" and $get_trgma=="Shona"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=sn&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}
if($data=="Sindhi"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Sindhi",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Sindhi");
}
if ($text != "/start" and $get_trgma=="Sindhi"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=sd&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Sinhala (Sinhalese)"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Sinhala (Sinhalese)",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Sinhala (Sinhalese)");
}
if ($text != "/start" and $get_trgma=="Sinhala (Sinhalese)"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=si&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Slovak"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Slovak",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Slovak");
}
if ($text != "/start" and $get_trgma=="Slovak"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=sk&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Slovenian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Slovenian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Slovenian");
}
if ($text != "/start" and $get_trgma=="Slovenian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=sl&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Somali"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Somali",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Somali");
}
if ($text != "/start" and $get_trgma=="Somali"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=so&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Spanish"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Spanish",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Spanish");
}
if ($text != "/start" and $get_trgma=="Spanish"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=es&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Sundanese"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Sundanese",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Sundanese");
}
if ($text != "/start" and $get_trgma=="Sundanese"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=su&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Swahili"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Swahili",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Swahili");
}
if ($text != "/start" and $get_trgma=="Swahili"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=sw&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Swedish"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Swedish",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Swedish");
}
if ($text != "/start" and $get_trgma=="Swedish"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=sv&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Tagalog (Filipino)"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Tagalog (Filipino)",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Tagalog (Filipino)");
}
if ($text != "/start" and $get_trgma=="Tagalog (Filipino)"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=tl&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}
if($data=="Tajik"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Tajik",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Tajik");
}
if ($text != "/start" and $get_trgma=="Tajik"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=tg&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Tamil"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Tamil",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Tamil");
}
if ($text != "/start" and $get_trgma=="Tamil"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ta&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Tatar"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Tatar",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Tatar");
}
if ($text != "/start" and $get_trgma=="Tatar"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=tt&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Telugu"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Telugu",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Telugu");
}
if ($text != "/start" and $get_trgma=="Telugu"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=te&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Thai"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Thai",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Thai");
}
if ($text != "/start" and $get_trgma=="Thai"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=th&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Turkish"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Turkish",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Turkish");
}
if ($text != "/start" and $get_trgma=="Turkish"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=tr&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Turkmen"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Turkmen",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Turkmen");
}
if ($text != "/start" and $get_trgma=="Turkmen"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=tk&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Ukrainian"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Ukrainian",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Ukrainian");
}
if ($text != "/start" and $get_trgma=="Ukrainian"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=uk&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Urdu"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Urdu",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Urdu");
}
if ($text != "/start" and $get_trgma=="Urdu"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ur&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Uyghur"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Urdu",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Uyghur");
}
if ($text != "/start" and $get_trgma=="Uyghur"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=ug&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}
if($data=="Uzbek"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Urdu",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Uzbek");
}
if ($text != "/start" and $get_trgma=="Uzbek"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=uz&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Vietnamese"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Urdu",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Vietnamese");
}
if ($text != "/start" and $get_trgma=="Vietnamese"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=vi&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Welsh"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Welsh",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Welsh");
}
if ($text != "/start" and $get_trgma=="Welsh"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=cy&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Xhosa"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Xhosa",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Xhosa");
}
if ($text != "/start" and $get_trgma=="Xhosa"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=xh&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}


if($data=="Yiddish"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Yiddish",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Yiddish");
}
if ($text != "/start" and $get_trgma=="Yiddish"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=yi&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>"`$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Yoruba"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Yoruba",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Yoruba");
}
if ($text != "/start" and $get_trgma=="Yoruba"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=yo&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>" `$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

if($data=="Zulu"){
bot('editmessagetext',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"❍ سيتم الترجمة إلى Zulu",
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
'parse_mode'=>"markdown",
]);
file_put_contents("chat_id/$chat_id/trgm.txt","Zulu");
}
if ($text != "/start" and $get_trgma=="Zulu"){
$api = file_get_contents("https://مسار استضافتك/api35.php?from=auto&to=zu&text=$text");
bot("SendMessage",[
"chat_id"=>$chat_id,
"text"=>" `$api`","reply_to_message_id"=>$message->message_id,
"parse_mode"=>"markdown"
]);
file_put_contents("chat_id/$chat_id/trgm.txt","");
}

?>


echo " 
