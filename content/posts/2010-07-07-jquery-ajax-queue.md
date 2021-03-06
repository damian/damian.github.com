+++
title = "jQuery Ajax Queue"
date = "2010-07-07"
+++

The need to perform synchronous AJAX calls sometimes arises, for example if your passing tokens back and forth for security reasons. <a href="http://jquery.com/">jQuery</a> makes such calls dead easy, all you have to do is set the 'async' option to false when setting up the AJAX handler.

{{< highlight javascript >}}
$('.click-me').bind('click', function(e){
  e.preventDefault();
  $.ajax({
    url: 'someurl',
    async: false,
    success: function(data) {
      console.log('blocking');
    }
  });
});
{{< / highlight >}}

The problem of this approach is that the browser locks up if the server takes a long time to respond. Because this is quite likely(heavy load during peak times etc) this would be damaging to the user experience. The ideal solution would be queue up AJAX requests without the browser locking up at all.

Because Google can't answer everything, I managed to come up with the following non blocking solution using <a href="http://api.jquery.com/queue/">queue</a>, a function&nbsp;that's part of jQuery core.

{{< highlight javascript >}}
$('.click-me').bind('click', function(e){
  e.preventDefault();
  $(document).queue(function() {
    $.ajax({
      url: 'someurl',
      success: function(data) {
        console.log('non blocking');
        $(document).dequeue();
      }
    });
  });
});
{{< / highlight >}}
