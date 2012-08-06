TCGA.intent
===========

TCGA.intent enables you to download files from the open-access HTTP directory of [The Cancer Genome Atlas (TCGA)](http://cancergenome.nih.gov/) from within the browser—without using or maintaining a proxy server. TCGA.intent uses [Web Intents](http://webintents.org/), a service discovery and light-weight RPC mechanism for Web apps.
All you have to do to use TCGA.intent in your Web app is to create an Intent that uses the following action–type combination: `http://mathbiol.org/intents/tcga/download [text/uri-list]`

Here is a minimal example to get you started:

    var Intent = Intent || WebKitIntent;
    window.navigator.webkitStartActivity(new Intent({
        "action": "http://mathbiol.org/intents/tcga/download",
        "type": "text/uri-list",
        "data": "FIRST_URI \n SECOND_URI \n THIRD_URI \n ..."
    }), function (result) {
        // The success callback.
    }, function (error) {
        // The error callback.
    });
