////////////////////////////////////////////////////////////////////////////////////
/// Bot feito por -Psyko-Matt-                                                                                                  
/// Edições e alguns comandos foram feitos por mim -TheMars                                              
///////////////////////////////////////////////////////////////////////////////////
easyBot = {
comandoslink: "http://goo.gl/Koy0Fe",
contatolink: "http://goo.gl/9DowgB",
awlink: "http://goo.gl/naCPwx",
blockskip: "on",
rdjpromo: "off",
versao: "2.0",
fdpta: "on",
};


easyBot.roleta = {
                roletaStatus: false,
                participants: [],
                countdown : null,
                startroleta: function(){
                    easyBot.roleta.roletaStatus = true;
                    easyBot.roleta.countdown = setTimeout(function(){ easyBot.roleta.endroleta(); }, 60 * 1000);
                    API.sendChat(":white_check_mark: A roleta foi iniciada! Digite !entrar para participar!");
                },
                endroleta: function(){
                    easyBot.roleta.roletaStatus = false;
                    var ind = Math.floor(Math.random() * easyBot.roleta.participants.length);
                    var winner = easyBot.roleta.participants[ind];
                    easyBot.roleta.participants = [];
                    var pos = 1;
                    var user = API.getUser(winner);
                    var name = user.username;
                    API.sendChat("A roleta acabou e um vencedor foi escolhido! @" + name + " :warning:");
                    setTimeout(function(winner){
                        API.moderateMoveDJ(winner, pos, false);
                    }, 1*1000, winner, pos);

     },
}

var botname = "easyBot";

////////////////////////////////////////////////////////////////////////////////
API.sendChat(botname +" está ativo, use a função !comandos para ver os comandos do bot! :warning:");
////////////////////////////////////////////////////////////////////////////////
var blockedSongs = [
    "MC"
];

var blockedArtists = [
    "MC"
];
////////////////////////////////////////////////////////////////////////////////
API.on(API.DJ_ADVANCE, listener);
function listener(data)
{
if (data == null)
{
return;
}

var title = data.media.title;
var author = data.media.author;
for (var i = 0; i < blockedSongs.length; i++)
{
if (easyBot.blockskip === "on") {
if (title.indexOf(blockedSongs[i]) != -1 || author.indexOf(blockedArtists[i]) != -1)
{
API.moderateForceSkip();
API.sendChat(title +": contra as regras e/ou fora dos temas permitidos!");
return;
}
}
}
}
///////////////PROMO////////////////////////////////////////////////////////////
API.on(API.USER_JOIN, rdjpromo);
function rdjpromo(user){
if (easyBot.rdjpromo === "on") {
API.moderateSetRole(user.id, API.ROLE.RESIDENTDJ);
}
}
////////////////////////////////////////////////////////////////////////////////
API.on(API.USER_JOIN, UserJoin2);
function UserJoin2(user){
if (easyBot.UserJoin2 === "on") {
setTimeout (function(){
API.sendChat("Olá " + "@" + user.username + ", bem-vindo.");
}, 1000);
}
}
//////////////////////////////////////////////////////////////////////////////////
function SecondsToHMS(d)
{
     d = Number(d);
     var h = Math.floor(d / 3600);
     var m = Math.floor(d % 3600 / 60);
     var s = Math.floor(d % 3600 % 60);
     return ((h > 0 ? (h >= 10 ? h : '0' + h): '00') + ':' + (m > 0 ? (m >= 10 ? m : '0' + m): '00') + ':' + (s > 0 ? (s >= 10 ? s : '0' + s): '00')  );
}
/////////////////////////////////////////////////////////////////////////////////
API.on(API.CURATE_UPDATE, curate);
function curate(obj) {
var media = API.getMedia();
if (easyBot.curate === "on"){
setTimeout (function(){
API.sendChat("/me@" + obj.user.username + " Adicionou a música " + media.author + " - " + media.title + " :warning:");
}, 1000);
}
}
/////////////////////////////////////////////////////////////////////////////////
API.on(API.USER_LEAVE, UserLeave);
function UserLeave(user){
if (easyBot.UserLeave === "on") {
setTimeout (function(){
API.sendChat("@" + user.username + ", saiu da sala.");
}, 1000);
}
}
////////////////////////////////////////////////////////////////////////////////
API.on(API.VOTE_UPDATE, lecau);
function lecau(obj) {
var vote = obj.vote == 1 ? "woot" : "meh";
if (vote == "woot"){
easyBot.fdpta = "off";
}
};
////////////////////////////////////////////////////////////////////////////////
API.on(API.DJ_ADVANCE, upup);
function upup(update) {
var hist = API.getHistory();
var djID = API.getHistory()[0].user.id;
for (var i in hist) {
if (hist[i].media.id == update.media.id) {
if (easyBot.upup === "on") {
API.sendChat("@"+ API.getDJ().username +" Esse video está no histórico!");
API.moderateForceSkip();
break;
}
}
}
}
////////////////////////////////////////////////////////////////////////////////
API.on(API.CHAT, plug);
function plug(data) {
var username = data.from;
var id = data.fromID;
var msg = data.message;
if (msg.indexOf("http://plug.dj/") > -1) {
API.moderateDeleteChat(data.chatID);
API.sendChat("/me["+ username + "] Por favor não divulgue outras salas do plug. :warning:");
}
}
////////////////////////////////////////////////////////////////////////////////
tacos = new Array();
tacos = ["cigarro","cigarro de maconha","marlboro","nargs","caximbo da paz"];
cookie = ["um biscoito de chocolate","um cupcake","um cookie de aveia e passas","um brownie 'especial'","um cracker animal","um lanche Scooby"];
drink = ["Caipirinha", "Wisk", "Tequila", "Champagne", "Martini", "Capeta"];
abraco = ["deu um abraço de urso em","deu um abraço gostosinho em","da um abraço por traz de","da um abraço de motoqueiro em"];
safado = ["morde a orelha de","aperta a bundinha de","lambe os mamilos de","morde os lábios de","faz um 69 com","lambe o umbigo de","chupa o dedo de","lambe a virilha de","Lambe os peitos de","Aperta as teta de"];
punirr = ["penetra uma caneta em","cutuca os olhos de","aperta os mamilos de","cospe em"];
punir2 = ["dá uma piruzada na cara de","passa DST para","penetra um dildo em","enfia um peixe elétrico no rabo de","da um tapa no saco de"];
////////////////////////////////////////////////////////////////////////////////
easyBotbot = {
falaoi: ["oi bot","ola bot","eae bot","olá bot"],
respondeoi: [":D Oi",":D Olá"],
boton: ["bot on?","bot tae?","bot esta ativado?","bot ta ativado?","bot ta on?","bot ligado?"],
toon: ["Estou aqui"],
olapessoas: ["oi gente","yo minna","ola pessoas","ola gente","eae galera","oi galera","eae gente","ola galera","eae","yo gente","oi pessoas","oi pessoal","oi"],
bomdia: ["bom dia gente","bom dia galera","bom dia pessoal"], bomdiabot: [":D Bom  Dia"],
boatarde: ["boa tarde gente","boa tarde galera","boa tarde pessoal"], boatardebot: [":D Boa  Tarde"],
boanoite: ["boa noite gente","boa noite galera","boa noite pessoal"], boanoitebot: [":D Boa  Noite"],
comandoslink: ["Link dos comandos: http://goo.gl/Koy0Fe"], clink: ["qual sao os comandos bot","link dos comandos bot","comandos da sala bot","qual são os comandos bot"],
regraslink: ["Clique no nome da sala para ver as regras."], rlink: ["qual sao as regras bot","link das regras bot","regras da sala bot","qual são as regras bot"],
autowootlink: ["Como usar Auto-Woot  > "+easyBot.awlink+" !"],
awlink: ["link do autowoot bot","como usar autowoot","o que é autowoot","como usa o autowoot"]
};
////////////////////////////////////////////////////////////////////////////////
API.on(API.CHAT,onChat);
function onChat(data) {
var message = data.message.toLowerCase();
var msg = data.message;
var arg1 = msg.split(" ")[1];
var ID = data.fromID;
var chat = data.chatID;
////////////////////////////////////////////////////////////////////////////////
if (message.indexOf("!") == 0) {
API.moderateDeleteChat(chat);
}
////////////////////////////////////////////////////////////////////////////////

//Admins Commands
// Permissions > 0 = Normal User, 1 = Bouncer, 2 = Manager, 3 = Co-Host

if(data.message.indexOf('!') === 0){
var msg = data.message, from = data.from, fromID = data.fromID;
var command = msg.substring(1).split(' ')
deleteAll = true;
if(typeof command[2] != "undefined"){
for(var i = 2; i<command.length; i++){
command[1] = command[1] + ' ' + command[i];
}
}
switch(command[0].toLowerCase()){
////////////////////////////////////////////////////////////////////////////////
case "rel":
if(API.getUser(ID).permission > 3 || Bot.admins.indexOf(ID) > -1){
API.sendChat("["+data.from+"] Religou o bot. :warning:");
API.off(API.DJ_ADVANCE, listener);
API.off(API.USER_JOIN, rdjpromo);
API.off(API.USER_JOIN, UserJoin2);
API.off(API.USER_LEAVE, UserLeave);
API.off(API.DJ_ADVANCE, upup);
API.off(API.CHAT,onChat);
API.off(API.CHAT,onChat2);
API.off(API.CHAT, inte);
API.off(API.VOTE_UPDATE, lecau);
setTimeout (function() {
$.getScript("Coloque aqui o link aonde você hospedou este script!");
}, 1500);
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Co anfitrião]");
}
break;

case "desl":
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1){
API.sendChat(botname + " está agora offline. :warning:");
API.off(API.DJ_ADVANCE, listener);
API.off(API.USER_JOIN, rdjpromo);
API.off(API.CURATE_UPDATE, curate);
API.off(API.USER_JOIN, UserJoin2);
API.off(API.USER_LEAVE, UserLeave);
API.off(API.DJ_ADVANCE, upup);
API.off(API.CHAT,onChat);
API.off(API.CHAT,onChat2);
API.off(API.CHAT, inte);
API.off (API.CHAT, log);
API.off(API.VOTE_UPDATE, lecau);
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Coordenador]");
}
break;
////////////////////////////////////////////////////////////////////////////////

////////////////////////////////////////////////////////////////////////////////
case "travar":
if(API.getUser(ID).permission > 1 || Bot.admins.indexOf(ID) > -1){
API.moderateLockWaitList(true);
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Segurança]");
}
break;
case "destravar":
if(API.getUser(ID).permission > 1 || Bot.admins.indexOf(ID) > -1){
API.moderateLockWaitList(false);
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Segurança]");
}
break;
////////////////////////////////////////////////////////////////////////////////
case "pular":
if(API.getUser(ID).permission > 1 || Bot.admins.indexOf(ID) > -1){
API.moderateForceSkip();
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Segurança]");
}
break;
////////////////////////////////////////////////////////////////////////////////
case "entrar":
var lista = API.getWaitListPosition(data.fromID);
if(lista === -1){
API.sendChat("@"+ data.from +" entre na lista para poder participar da roleta! :warning:");
}else{
if(easyBot.roleta.roletaStatus){
easyBot.roleta.participants.push(data.fromID);
}
}
break;
              
case "sair":
var ind = easyBot.roleta.participants.indexOf(data.fromID);
if(ind > -1){
easyBot.roleta.participants.splice(ind, 1);
API.sendChat("@" + data.from + " saiu da roleta! :warning:");
}
break;

case "roleta":
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1) {
if(!easyBot.roleta.roletaStatus){
easyBot.roleta.startroleta();
}
}else{
API.sendChat("@"+ data.from +" Você não tem permissão para usar este comando! [+Coordenador]");
}
break;

case "stoproleta":
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1) {
if(easyBot.roleta.roletaStatus === true){
API.sendChat("A roleta foi parada :warning:");
easyBot.roleta.roletaStatus = false;
clearTimeout(easyBot.roleta.countdown);
}
}else{
API.sendChat("@"+ data.from +" Você não tem permissão para usar este comando! [+Coordenador]");
}
break;
////////////////////////////////////////////////////////////////////////////////
case "eta":
var rem = API.getTimeRemaining();
var wlPos = API.getWaitListPosition(data.fromID);
var tempoRes;  
if( wlPos === -1 )
{
tempoRes = (210*(wlPos+1)) + rem;
API.sendChat('['+ data.from +'] Entre na lista de espera antes de usar o !eta :warning:');
}
else
{
tempoRes = (210*wlPos)+rem;
    
if(tempoRes < "6")
{
}
else{
API.sendChat("["+ data.from +"] Você será o dj em: " + SecondsToHMS(tempoRes)); 
}
}
break;
////////////////////////////////////////////////////////////////////////////////
case "f5":
if(API.getUser(ID).permission > 3 || Bot.admins.indexOf(ID) > -1){
setTimeout(function() {
API.sendChat("/me["+data.from+"] Atualizando a página... Bye");
$("#chat-messages").append("<div class='Blue system'><i class='icon icon-refresh-video'></i><span class='text'> Atualizando a página...</span></div>");
location.reload(true);
}, (1*1000));
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Co anfitrião]");
}
break;
case "putaria":
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1){
if (arg1 === "on") {
easyBot.blockskip = "on";
API.sendChat("/meVideos bloqueados ativados!");
}
if (arg1 === "off") {
easyBot.blockskip = "off";
API.sendChat("/meVideos bloqueados desativados!");
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Coordenador]");
}
break;
case "htfilter":
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1){
if (arg1 === "on") {
easyBot.upup = "on";
API.sendChat("/meFiltro de histórico [Ativado] :warning:");
}
if (arg1 === "off") {
easyBot.upup = "off";
API.sendChat("/meFiltro de histórico [Desativado] :warning:");
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Coordenador]");
}
break;
case "msgrab":
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1){
if (arg1 === "on"){
easyBot.curate = "on";
API.sendChat("/meMensagem de Grabs [Ativado] :warning:");
}
if (arg1 === "off") {
easyBot.curate = "off";
API.sendChat("/meMensagem de Grabs  [Desativado] :warning:");
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Coordenador]");
}
break;
case "rdjpromo":
if(API.getUser(ID).permission > 3 || Bot.admins.indexOf(ID) > -1){
if (arg1 === "on") {
easyBot.rdjpromo = "on";
API.sendChat("/meDJ Residente para os que entrarem na sala [Ativado]");
}
if (arg1 === "off") {
easyBot.rdjpromo = "off";
API.sendChat("/meDJ Residente para os que entrarem na sala [Desativado]");
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Co anfitrião]");
}
break;
case "msg":
if(API.getUser(ID).permission > 3 || Bot.admins.indexOf(ID) > -1){
if (arg1 === "on") {
easyBot.UserJoin2 = "on";
API.sendChat("/meMensagem de boas-vindas [Ativado] :warning:");
}
if (arg1 === "off") {
easyBot.UserJoin2 = "off";
API.sendChat("/meMensagem de boas-vindas  [Desativado] :warning: ");
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Co anfitrião]");
}
break;

case "leave":
if(API.getUser(ID).permission > 3 || Bot.admins.indexOf(ID) > -1){
if (arg1 === "on") {
easyBot.UserLeave = "on";
API.sendChat("/meMensagem de saída [Ativado] :warning:");
}
if (arg1 === "off") {
easyBot.UserLeave = "off";
API.sendChat("/meMensagem de saída  [Desativado] :warning: ");
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Co anfitrião]");
}
break;

case "woot":
$("#woot").click();
break;
case "meh":
$("#meh").click();
break;
////////////////////////////////////////////////////////////////////////////////
case "limparchat":
case "clearchat":
case "clear":
case "apagarchat":
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1){
var arg = $("#chat-messages").children();
for(var i=0;i<arg.length;i++) API.moderateDeleteChat(arg[i].className.substr(arg[i].className.indexOf('cid-')+4,14));
deleteAll = true;
setTimeout(function(){
}, 150);
API.sendChat("[" + data.from + "]" + " Apagou o Chat. :warning:");
setTimeout(function(){
}, 950);
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando. [+ Coordenador]");
}
break;
////////////////////////////////////////////////////////////////////////////////
case "infosg":
if(API.getUser(ID).permission > 1){
API.sendChat("/me Acesse nosso Blog: http://goo.gl/DN0uLa");
API.sendChat("/me Curta nossa página no facebook: http://goo.gl/sCLUNI");
API.sendChat("/me Comandos "+easyBot.comandoslink+" !");
}
break;
////////////////////////////////////////////////////////////////////////////////
//User Commands
////////////////////////////////////////////////////////////////////////////////

case "djinfo":
{
var total = API.getDJ().djPoints + API.getDJ().listenerPoints + API.getDJ().curatorPoints;
API.sendChat("DJ atual: "+ API.getDJ().username +". Pontos: "+ total +" | Fans: "+ API.getDJ().fans +" | Adds: "+ API.getDJ().curatorPoints +".");
}
break;

case "pontos":
case "points":
API.sendChat ("@" + data.from +" :+1: "+ API.getUser(data.fromID).listenerPoints +" | :sound: "+ API.getUser(data.fromID).djPoints +" | :star: "+ API.getUser(data.fromID).curatorPoints +".");
break;

case "host":
API.sendChat ("/me[" + data.from +"], o dono da sala é o @"+ API.getHost().username);
break;
////////////////////////////////////////////////////////////////////////////////
case "meuid":
{
API.sendChat("Username: "+ data.from +" ID: "+ data.fromID);
}
break;
////////////////////////////////////////////////////////////////////////////////
case "legal":
{
API.sendChat("@"+ data.from +" gostou pra carolho do seu video @"+ API.getDJ().username +", continue assim!");
}
break;
case "chato":
{
API.sendChat("@"+ data.from +" não gostou desse seu video de merda @"+ API.getDJ().username +", melhore na proxima! :-1: :broken_heart: ");
}
break;
////////////////////////////////////////////////////////////////////////////////
case "nocéutempão":
case "pão":
API.sendChat("/me["+data.from+"] E morreu...");
break;
case "sexoanal":
case "comervagina":
API.sendChat("/me["+data.from+"] Chupa uns cu e pá.. :trollface:");
break;
case "comandos":
API.sendChat("/me["+data.from+"] Clique no link para ver os comandos: "+ easyBot.comandoslink +" !");
break;
case "regras":
case "temas":
API.sendChat("/me["+data.from+"] Clique no nome da sala para ver as regras e os temas.");
break;
case "fb":
API.sendChat("/meCurta nossa página no facebook: http://goo.gl/ougf7N");
break;
case "tuto":
API.sendChat ("/meAprenda mais sobre e como usar o plug.dj > http://goo.gl/SJmV0t");
brak;
case "adblock":
API.sendChat("/mePara remover as propagandas dos videos use AdBlock > http://www.adblockplus.org/");
break;
case "autowoot":
API.sendChat("/meTutorial Auto-woot "+easyBot.awlink);
break;
case "blog":
API.sendChat("/meAcesse o blog http://goo.gl/DN0uLa");
break;
case "dg":
API.sendChat ("/meVeja todos os diálogos do bot aqui http://goo.gl/NlFZmP");
break;
case "yt":
API.sendChat("/meAcesse meu canal no Youtube http://goo.gl/O38Cmj");
break;
case "contato":
API.sendChat("/meAcesse o link "+ easyBot.contatolink +", e entre em conosco.");
break;
////////////////////////////////////////////////////////////////////////////////
case "musica":
if(API.getMedia().format == 1){
API.sendChat("@" + data.from + " " + "http://youtu.be/" + API.getMedia().cid);
}else{
var id = API.getMedia().cid;
SC.get('/tracks', { ids: id,}, function(tracks) {
API.sendChat("@"+data.from+" "+tracks[0].permalink_url);
});
}
break;

////////////////////////////////////////////////////////////////////////////////
case "diz":
if (API.getUser(data.fromID).permission > 1){
API.sendChat(command[1]);
}
break;
////////////////////////////////////////////////////////////////////////////////

////////////////////////////////////////////////////////////////////////////////
case "aw":
if(typeof command[1] == "@"){
var crowd = API.getUsers();
var randomUser = Math.floor(Math.random() * crowd.length);
var randomPunirr = Math.floor(Math.random() * punirr.length);
var randomSentence = Math.floor(Math.random() * 1);
switch(randomSentence){
case 0:
API.sendChat("@"+command[1]+" clique no link e veja como usar auto-woot > "+ easyBot.awlink);
break;
}
}else{
if(command[1].indexOf("@") === 0) command[1] = command[1].substring(1);
var randomPunirr = Math.floor(Math.random() * punirr.length);
var randomSentence = Math.floor(Math.random() * 1);
switch(randomSentence){
case 0:
API.sendChat("@"+command[1]+" clique no link e veja como usar auto-woot > "+ easyBot.awlink);
break;
}

}
break;
////////////////////////////////////////////////////////////////////////////////
case "punir":
if(typeof command[1] == "@"){
var crowd = API.getUsers();
var randomUser = Math.floor(Math.random() * crowd.length);
var randomPunirr = Math.floor(Math.random() * punirr.length);
var randomSentence = Math.floor(Math.random() * 1);
switch(randomSentence){
case 0:
API.sendChat("@"+data.from+" "+punirr[randomPunirr]+" @"+command[1]+" ");
break;
}
}else{
if(command[1].indexOf("@") === 0) command[1] = command[1].substring(1);
var randomPunirr = Math.floor(Math.random() * punirr.length);
var randomSentence = Math.floor(Math.random() * 1);
switch(randomSentence){
case 0:
API.sendChat("@"+data.from+" "+punirr[randomPunirr]+" @"+command[1]+" ");
break;
}

}
break;

case "punir2":
if(typeof command[1] == "@"){
var crowd = API.getUsers();
var randomUser = Math.floor(Math.random() * crowd.length);
var randomPunir2 = Math.floor(Math.random() * punir2.length);
var randomSentence = Math.floor(Math.random() * 1);
switch(randomSentence){
case 0:
API.sendChat("@"+data.from+" "+punir2[randomPunir2]+" @"+command[1]+" ");
break;
}
}else{
if(command[1].indexOf("@") === 0) command[1] = command[1].substring(1);
var randomPunir2 = Math.floor(Math.random() * punir2.length);
var randomSentence = Math.floor(Math.random() * 1);
switch(randomSentence){
case 0:
API.sendChat("@"+data.from+" "+punir2[randomPunir2]+" @"+command[1]+" ");
break;
}

}
break;
////////////////////////////////////////////////////////////////////////////////
case "cookie":
if(typeof command[1] == "@"){
var crowd = API.getUsers();
var randomUser = Math.floor(Math.random() * crowd.length);
var randomCookie = Math.floor(Math.random() * cookie.length);
var randomSentence = Math.floor(Math.random() * 3);
switch(randomSentence){
case 0:
API.sendChat("@" +command[1]+ ", @" + data.from + " recompensou-lhe com " + cookie[randomCookie]+ ". Divirta-se!");
break;
case 1:
API.sendChat("@" +command[1]+ ", @" + data.from + " recompensou-lhe com " + cookie[randomCookie]+ ". Divirta-se!");
break;
case 2:
API.sendChat("@" +command[1]+ ", @" + data.from + " recompensou-lhe com " + cookie[randomCookie]+ ". Divirta-se!");
break;
}
}else{
if(command[1].indexOf("@") === 0) command[1] = command[1].substring(1);
var randomCookie = Math.floor(Math.random() * cookie.length);
var randomSentence = Math.floor(Math.random() * 3);
switch(randomSentence){
case 0:
API.sendChat("@" +command[1]+ ", @" + data.from + " recompensou-lhe com " + cookie[randomCookie]+ ". Divirta-se!");
break;
case 1:
API.sendChat("@" +command[1]+ ", @" + data.from + " recompensou-lhe com " + cookie[randomCookie]+ ". Divirta-se!");
break;
case 2:
API.sendChat("@" +command[1]+ ", @" + data.from + " recompensou-lhe com " + cookie[randomCookie]+ ". Divirta-se!");
break;
}}
break;
////////////////////////////////////////////////////////////////////////////////
case "drink":
if(typeof command[1] == "@"){
var crowd = API.getUsers();
var randomUser = Math.floor(Math.random() * crowd.length);
var randomDrink = Math.floor(Math.random() * drink.length);
var randomSentence = Math.floor(Math.random() * 2);
switch(randomSentence){
case 0:
API.sendChat("@" +command[1]+ ", @" + data.from + " recompensou-lhe com " + drink[randomDrink]+ ". Divirta-se!");
break;
case 1:
API.sendChat("@" +command[1]+ ", @" + data.from + " recompensou-lhe com " + drink[randomDrink] + ". Divirta-se!");
break;
case 2:
API.sendChat("@" +command[1]+ ", @" + data.from + " recompensou-lhe com " + drink[randomDrink] + ". Divirta-se!");
break;
}
}else{
if(command[1].indexOf("@") === 0) command[1] = command[1].substring(1);
var randomDrink = Math.floor(Math.random() * drink.length);
var randomSentence = Math.floor(Math.random() * 2);
switch(randomSentence){
case 0:
API.sendChat("@" +command[1]+ ", @" + data.from + " recompensou-lhe com " + drink[randomDrink] + ". Divirta-se!");
break;
}
}
break;
////////////////////////////////////////////////////////////////////////////////
case "drugs":
if(typeof command[1] == "@"){
var crowd = API.getUsers();
var randomUser = Math.floor(Math.random() * crowd.length);
var randomTaco = Math.floor(Math.random() * tacos.length);
var randomSentence = Math.floor(Math.random() * 3);
switch(randomSentence){
case 0:
API.sendChat("@" + crowd[randomUser].username + ", fuma esse " + tacos[randomTaco] + ", seu vagabundo!");
break;
case 1:
API.sendChat("@" + crowd[randomUser].username + ", pega um " + tacos[randomTaco] + " ae bro!");
break;
case 2:
API.sendChat("Um " + tacos[randomTaco] + " para você, @" + crowd[randomUser].username + ".");
break;
case 3:
API.sendChat(" deu " + tacos[randomTaco] + " para @" + crowd[randomUser].username + "!");
break;
}
}else{
if(command[1].indexOf("@") === 0) command[1] = command[1].substring(1);
var randomTaco = Math.floor(Math.random() * tacos.length);
var randomSentence = Math.floor(Math.random() * 3);
switch(randomSentence){
case 0:
API.sendChat("@" + command[1] + ", fuma esse " + tacos[randomTaco] + ", seu vagabundo!");
break;
case 1:
API.sendChat("@" + command[1] + ", pega um " + tacos[randomTaco] + " ae bro!");
break;
case 2:
API.sendChat("Um " + tacos[randomTaco] + " para você, @" + command[1] + ".");
break;
case 3:
API.sendChat(" Deu " + tacos[randomTaco] + " para @" + command[1] + "!");
break;
}}
break;
////////////////////////////////////////////////////////////////////////////////
case "safado":
if(typeof command[1] == "@"){
var crowd = API.getUsers();
var randomUser = Math.floor(Math.random() * crowd.length);
var randomSafado = Math.floor(Math.random() * safado.length);
var randomSentence = Math.floor(Math.random() * 2);
switch(randomSentence){
case 0:
API.sendChat("@"+data.from+" "+safado[randomSafado]+" @"+command[1]+"!");
break;
}
}else{
if(command[1].indexOf("@") === 0) command[1] = command[1].substring(1);
var randomSafado = Math.floor(Math.random() * safado.length);
var randomSentence = Math.floor(Math.random() * 1);
switch(randomSentence){
case 0:
API.sendChat("@"+data.from+" "+safado[randomSafado]+" @"+command[1]+"!");
break;
}
}
break;
case "abraço":
if(typeof command[1] == "@"){
var crowd = API.getUsers();
var randomUser = Math.floor(Math.random() * crowd.length);
var randomAbraco = Math.floor(Math.random() * abraco.length);
var randomSentence = Math.floor(Math.random() * 2);
switch(randomSentence){
case 0:
API.sendChat("@"+data.from+" "+abraco[randomAbraco]+" @"+command[1]+"!");
break;
}
}else{
if(command[1].indexOf("@") === 0) command[1] = command[1].substring(1);
var randomAbraco = Math.floor(Math.random() * abraco.length);
var randomSentence = Math.floor(Math.random() * 1);
switch(randomSentence){
case 0:
API.sendChat("@"+data.from+" "+abraco[randomAbraco]+" @"+command[1]+"!");
break;
}
}
break;
}
}
}
////////////////////////////////////////////////////////////////////////////////
API.on(API.CHAT, inte);
function inte(data){
msg = data.message.toLowerCase();

//Autowoot Link
for(var i = 0; i < easyBotbot.awlink.length; i++){
if(msg.indexOf(easyBotbot.awlink[i].toLowerCase()) > -1){
var autowootlinkRandom = Math.floor(Math.random() * easyBotbot.autowootlink.length);
API.sendChat(easyBotbot.autowootlink[autowootlinkRandom] +" @"+ data.from +" ");
}
}
//Comandos Link
for(var i = 0; i < easyBotbot.clink.length; i++){
if(msg.indexOf(easyBotbot.clink[i].toLowerCase()) > -1){
var comandoslinkRandom = Math.floor(Math.random() * easyBotbot.comandoslink.length);
API.sendChat(easyBotbot.comandoslink[comandoslinkRandom] +" @"+ data.from +" ");
}
}
//Regras Link
for(var i = 0; i < easyBotbot.rlink.length; i++){
if(msg.indexOf(easyBotbot.rlink[i].toLowerCase()) > -1){
var regraslinkRandom = Math.floor(Math.random() * easyBotbot.regraslink.length);
API.sendChat(easyBotbot.regraslink[regraslinkRandom] +" @"+ data.from +" ");
}
}
//Oi
for(var i = 0; i < easyBotbot.falaoi.length; i++){
if(msg.indexOf(easyBotbot.falaoi[i].toLowerCase()) > -1){
var respondeoiRandom = Math.floor(Math.random() * easyBotbot.respondeoi.length);
API.sendChat(easyBotbot.respondeoi[respondeoiRandom] +" @"+ data.from +" ");
}
}
//On?
for(var i = 0; i < easyBotbot.boton.length; i++){
if(msg.indexOf(easyBotbot.boton[i].toLowerCase()) > -1){
var toonRandom = Math.floor(Math.random() * easyBotbot.toon.length);
API.sendChat(easyBotbot.toon[toonRandom] +" @"+ data.from +" ");
}
}
//ola pessoas
for(var i = 0; i < easyBotbot.olapessoas.length; i++){
if(msg.indexOf(easyBotbot.olapessoas[i].toLowerCase()) > -1){
var welcomebotRandom = Math.floor(Math.random() * easyBotbot.welcomebot.length);
API.sendChat(easyBotbot.welcomebot[welcomebotRandom] +" @"+ data.from +" !");
}
}
//bomdia
for(var i = 0; i < easyBotbot.bomdia.length; i++){
if(msg.indexOf(easyBotbot.bomdia[i].toLowerCase()) > -1){
var bomdiabotRandom = Math.floor(Math.random() * easyBotbot.bomdiabot.length);
API.sendChat(easyBotbot.bomdiabot[bomdiabotRandom] +" @"+ data.from +" ");
}
}
//boatarde
for(var i = 0; i < easyBotbot.boatarde.length; i++){
if(msg.indexOf(easyBotbot.boatarde[i].toLowerCase()) > -1){
var boatardebotRandom = Math.floor(Math.random() * easyBotbot.boatardebot.length);
API.sendChat(easyBotbot.boatardebot[boatardebotRandom] +" @"+ data.from +" ");
}
}
//boanoite
for(var i = 0; i < easyBotbot.boanoite.length; i++){
if(msg.indexOf(easyBotbot.boanoite[i].toLowerCase()) > -1){
var boanoitebotRandom = Math.floor(Math.random() * easyBotbot.boanoitebot.length);
API.sendChat(easyBotbot.boanoitebot[boanoitebotRandom] +" @"+ data.from +" ");
}
}

}//);
////////////////////////////////////////////////////////////////////////////////

var users = API.getUsers();

function getUserID(name) {
for (var i in users) {
if (users[i].username == name) {
return users[i].id;
}
}
return null;
}

API.on(API.CHAT,onChat2);
function onChat2(data) {
var message = "";

    var id = data.fromID;
    var msg = data.message;
    var userfrom = data.from;
    var userfromid = data.fromID;
    var getpos = API.getWaitListPosition(userfromid);
    var noargs = msg.substr(msg.indexOf(""));
    var cmd = (msg.split(" ")[0]).toLowerCase();
    var arg1 = msg.split(" ")[1];
    var arg2 = msg.split(" ")[2];
    var args = msg.substr(msg.indexOf(" ") + 1);
    var argsMotd = msg.substr(msg.indexOf(" ") + 5);
	var ID = data.fromID;
	var argname = arg1.slice(1, arg1.length);
	var userid = getUserID(argname);
	
if (cmd == "!add")
if(API.getUser(ID).permission > 1 || Bot.admins.indexOf(ID) > -1){
if (userid == null) {}else{
API.moderateAddDJ(userid);
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Segurança]");
}
if (cmd == "!kick")
if(API.getUser(ID).permission > 1 || Bot.admins.indexOf(ID) > -1){
if (userid == null) {}else{
API.moderateBanUser(userid, 0, API.BAN.HOUR);
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Segurança]");
}
if (cmd == "!ban")
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1){
if (userid == null) {}else {
API.moderateBanUser(userid, 0, API.BAN.PERMA);
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Coordenador]");
}
if (cmd == "!desbanir")
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1){
if (userid == null) {}else{
API.moderateUnbanUser(userid);
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Coordenador]");
}
if (cmd == "!bouncer")
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1){
if (userid == null) {}else{
API.moderateSetRole(userid, API.ROLE.BOUNCER);
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Coordenador]");
}
if (cmd == "!rdj")
if(API.getUser(ID).permission > 2 || Bot.admins.indexOf(ID) > -1){
if (userid == null) {}else{
API.moderateSetRole(userid, API.ROLE.RESIDENTDJ);
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Coordenador]");
}
if (cmd == "!rmv")
if(API.getUser(ID).permission > 1 || Bot.admins.indexOf(ID) > -1){
if (userid == null) {}else{
API.moderateRemoveDJ(userid);
}
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Segurança]");
}
//By easyBot
if (cmd == "!aviso")
if(API.getUser(ID).permission > 1 || Bot.admins.indexOf(ID) > -1){
API.sendChat("@"+argname+" Você tem 1 minuto para avaliar o vídeo caso contrario será removido da lista de djs.");
setTimeout (function() {
if (easyBot.fdpta === "on") {
API.sendChat("@"+argname+" Você foi removido da lista por não avaliar, use o comando !autowoot para isso não acontecer.");
API.moderateRemoveDJ(userid);
}
}, 60000);
}else{
API.sendChat("@" + data.from + ", você não tem permissão para usar este comando.[+ Segurança]");
}

}

////////////////////////////////////////////////////////////////////////////////

////////////////////////////////////////////////////////////////////////////////
