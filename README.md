# Current-tab-active-
How to keep the current tab active on page reload in Bootstrap


```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Keep Selected Bootstrap Tab Active on Page Refresh</title>
<link rel="stylesheet" href="css/bootstrap.min.css">
<link rel="stylesheet" href="css/bootstrap-theme.min.css">
<script src="https://code.jquery.com/jquery-1.11.2.min.js"></script>
<script src="js/bootstrap.min.js"></script>
<script>
$(document).ready(function(){
    $('a[data-toggle="tab"]').on('show.bs.tab', function(e) {
        localStorage.setItem('activeTab', $(e.target).attr('href'));
    });
    var activeTab = localStorage.getItem('activeTab');
    if(activeTab){
        $('#myTab a[href="' + activeTab + '"]').tab('show');
    }
});
</script>
</head>
<body>
    <ul class="nav nav-tabs" id="myTab">
        <li class="active"><a data-toggle="tab" href="#sectionA">Section A</a></li>
        <li><a data-toggle="tab" href="#sectionB">Section B</a></li>
        <li><a data-toggle="tab" href="#sectionC">Section C</a></li>
    </ul>
    <div class="tab-content">
        <div id="sectionA" class="tab-pane fade in active">
            <h3>Section A</h3>
            <p>Aliquip placeat salvia cillum iphone...</p>
        </div>
        <div id="sectionB" class="tab-pane fade">
            <h3>Section B</h3>
            <p>Vestibulum nec erat eu nulla rhoncus fringilla...</p>
        </div>
        <div id="sectionC" class="tab-pane fade">
            <h3>Section C</h3>
            <p>Nullam hendrerit justo non leo aliquet...</p>
        </div>
    </div>
</body>
</html>

```
