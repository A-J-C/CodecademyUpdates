```
javascript:(function(){try{var b=location.pathname.match(/\d+$/)[0]-1,c = CCDATA.composer.course.projects[CCDATA.composer.course.project_index],f=c.author.handle,h=CCDATA.composer.course.language.toLowerCase(),d=c.checkpoints[b].test_functions;if($.fn.modal){a()}else{$.getScript('//cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/2.3.1/js/bootstrap-modal.js').done(a).fail(function(j,i,k){throw k})}}catch(g){return console.log(g.message)}function a(){var j,e=$('#sct').length>0;if(e){j=$('#sct')}else{j=$('<div id=\'sct\' class=\'modal fade hide\' style=\'width:680px\'>').append($('<div class=\'modal-header\'>').append($('<button type=\'button\' class=\'close\' data-dismiss=\'modal\'>').text('×')).append('<h3>Correctness Test <small> &'+'nbsp; Course by '+f+'</small></h3>')).append($('<div class=\'modal-body\'>').append($('<pre>').html('<code></code>'))).append($('<div class=\'modal-footer\'>').append('<a target=\'blank\' href=\'//www.codecademy.com/docs/submission_tests\'>About Correctness Tests</a> &'+'nbsp;|&'+'nbsp;').append($('<button class=\'btn btn-small\' data-dismiss=\'modal\'>').text('Close'))).appendTo($('body'))}d=d.replace(/&/g,'&'+'amp;').replace(/</g,'&'+'lt;').replace(/>/g,'&'+'gt;');var i=j.find('code').eq(0).attr('class','language-'+(h=='web'?'javascript':h)).html(d);hljs&&hljs.highlightBlock(i.get(0));j.modal('show')}})();
```

And this is the code formated if you wanted to look through it:

```
javascript: (function () {
    try {
        var b = location.pathname.match(/\d+$/)[0] - 1,
            c = CCDATA.composer.course.projects[CCDATA.composer.course.project_index],
            f = c.author.handle,
            h = CCDATA.composer.course.language.toLowerCase(),
            d = c.checkpoints[b].test_functions;
        if ($.fn.modal) {
            a()
        } else {
            $.getScript('//cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/2.3.1/js/bootstrap-modal.js').done(a).fail(function (j, i, k) {
                throw k
            })
        }
    } catch (g) {
        return console.log(g.message)
    }

    function a() {
        var j, e = $('#sct').length > 0;
        if (e) {
            j = $('#sct')
        } else {
            j = $('<div id=\'sct\' class=\'modal fade hide\' style=\'width:680px\'>').append($('<div class=\'modal-header\'>').append($('<button type=\'button\' class=\'close\' data-dismiss=\'modal\'>').text('×')).append('<h3>Correctness Test <small> &' + 'nbsp; Course by ' + f + '</small></h3>')).append($('<div class=\'modal-body\'>').append($('<pre>').html('<code></code>'))).append($('<div class=\'modal-footer\'>').append('<a target=\'blank\' href=\'//www.codecademy.com/docs/submission_tests\'>About Correctness Tests</a> &' + 'nbsp;|&' + 'nbsp;').append($('<button class=\'btn btn-small\' data-dismiss=\'modal\'>').text('Close'))).appendTo($('body'))
        }
        d = d.replace(/&/g, '&' + 'amp;').replace(/</g, '&' + 'lt;').replace(/>/g, '&' + 'gt;');
        var i = j.find('code').eq(0).attr('class', 'language-' + (h == 'web' ? 'javascript' : h)).html(d);
        hljs && hljs.highlightBlock(i.get(0));
        j.modal('show')
    }
})();
```
  
To use it as a **bookmarklet** create a new 'bookmark' and in the URL slot of the bookmark copy and paste the top line of code.
Clcik on the new bookmark on any exercise and the SCT should be displayed.

Also credit to Alex J who made the original SCT Viewer which a lot of this is based of.
