# JQuery
```javascript
$("tr").hover(
    function() {
        $(this).css({
            "color":"white",
            "background-color":"#98bf21",
            "font-family":"Arial",
            "font-size":"20px",
            "padding":"5px"
        });
    }, 
    function() {
        $("tr").css({
            "color":"black",
            "background-color":"white",
            "font-family":"sans",
            "font-size":"16px",
            "padding":"0px"
        });
    }
);

$(function() {
    $( "#true_false_1" ).buttonset();

    $( "#mult_1" ).selectmenu();

    $( "#answers" ).dialog({
        autoOpen: false,
        show: {
            effect: "clip",
            duration: 500
        },
        hide: {
            effect: "clip",
            duration: 500
        }
    });
});
```