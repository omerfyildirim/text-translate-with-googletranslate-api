# text-translate-with-googletranslate-api
It translates texts any language to TR or the reverse.

First of all, we need to build a script on Google via Appscripts, after the script& its URL we're gonna build our projects
![image](https://github.com/omerfyildirim/text-translate-with-googletranslate-api/assets/106185278/f4e72829-cb98-4aaa-b4df-51e1d67334cd)
![image](https://github.com/omerfyildirim/text-translate-with-googletranslate-api/assets/106185278/af41d3b8-3d06-4ffa-8a9d-e7ba70b42a86)
![image](https://github.com/omerfyildirim/text-translate-with-googletranslate-api/assets/106185278/2ca318d4-5d5c-4e28-ad66-a1b125542e14)


and here the script code block:

var mock = {
  parameter:{
    q:'Merhaba Dünya!',
    source:'tr',
    target:'kr'
  }
};


function doGet(e) {
  e = e || mock;

  var sourceText = ''
  if (e.parameter.q){
    sourceText = e.parameter.q;
  }

  var sourceLang = '';
  if (e.parameter.source){
    sourceLang = e.parameter.source;
  }

  var targetLang = 'en';
  if (e.parameter.target){
    targetLang = e.parameter.target;
  }

  var translatedText = LanguageApp.translate(sourceText, sourceLang, targetLang, {contentType: 'html'});

  return ContentService.createTextOutput(translatedText).setMimeType(ContentService.MimeType.JSON);
}
