
<html>
    <head>
        <title>Internet Noise</title>
    </head>
    <body>
        <script src="https://code.jquery.com/jquery-2.2.4.min.js"
                integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44="
                crossorigin="anonymous"></script>
        <script>

            // Oh the irony
            (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
            (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
            m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
            })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

            ga('create', 'UA-96463715-1', 'auto');
            ga('send', 'pageview');

        </script>

        <script>
            var stop = false;
            var popups = {};
            var isFirst = 0;
            // I wrote this in 5 minutes and am tired. maybe I'll clean it up later.
            $(function() {

                var nouns = [ "Taylor Swift ours ", "taylor swift 22", "Taylor Swift", "taylor swift you belong with me",  "taylor swift mean",  "taylor swift wildest dreams",  "taylor swift blank space", "taylor swift fifteen"];

                function get_random_word() {
                    return nouns[Math.floor(Math.random()*nouns.length)];
                    //return ("Taylor Swift");
                }

                function lucky(words, name) {
                    if (isFirst == 0)
                    {
                        var url = "http://www.catbreedslist.com/fluffy-cat-breeds/#.WOHVjfnytPY";
                        window.open(url, name);                                                            
                        self.focus();
                        setTimeout(function() {
                        if(!stop)
                            noisify(name);
                    }, Math.floor(Math.random() * 8000) + 8000);
                    isFirst =1;
                    }
                    else
                    {
                    var url = "https://www.google.com/search?btnI&q=site:youtube.com+" + encodeURIComponent(words.join(" "));
                    //var url = "https://duckduckgo.com/?q=!ducky+"encodeURIComponent(words.join(" ")"+site%3Ayoutube.com";
                    /*if(name in popups
                    && !popups[name].closed) {
                        popups[name].location = url;
                    } else {
                        popups[name] = window.open(url, name);
                    }*/
                    window.open(url, name);                                                            
                    self.focus();
                    setTimeout(function() {
                        if(!stop)
                            noisify(name);
                    }, Math.floor(Math.random() * 8000) + 8000);
                    }
                }

                function noisify(name) {
                    stop = false;
                    var words = [];
                    words.push(get_random_word());
                   // words.push(get_random_word());
                    lucky(words, name);
                }

                $("#noise").click(function() {

                    noisify('noise_a');
                    noisify('noise_b');
                    noisify('noise_c');
                    noisify('noise_d');
                    noisify('noise_e');

                });
                $("#stop").click(function() {
                    stop = true;
                });
            })

        </script>

        <div style="max-width: 800px; margin: auto;">
            <h1>Internet Noise</h1>
            <p>On March 29th <a href="https://www.govtrack.us/congress/votes/115-2017/h202">congress passed a law</a> that makes it legal for your Internet Service Providers (ISP) to track and sell your personal activity online.  This means that things you search for, buy, read, and say can be collected by corporations and used against you.</p>

            <p>Click this button, and your browser will start passively loading random sites in browser tabs.  Leave it running to fill their databases with noise.  Just quit your browser when you're done.</p>

            <input type="button" value="Make some noise" id="noise"/>
            <input type="button" value="STOP THE NOISE!" id="stop"/>
            <br/>
            <br/>
            <p><i>This is an early stage and still evolving project. Please offer feedback <a href="https://twitter.com/taylorswift13">via twitter</a> and if something goes wrong let me know.</i></p>
            <br/>
            <hr/>
            <br/>

            <p><b>IMPORTANT: this button will make some noise as a form of digital protest.  IT DOES NOT MAKE YOU SAFE.</b></p>

            <p>If you are genuinely interested in thwarting the tracking efforts of your ISP and advertisers you should:</p>

            <ol>
                <li>Install <a href="https://www.eff.org/https-everywhere">HTTPS Everywhere</a> to ensure your web activities are encrypted as often as possible.</li>
                <li><a href="https://supporters.eff.org/donate/button">Donate to the EFF.</a></li>
                <li>Learn about <a href="https://slifty.com/2012/08/a-tor-of-the-dark-web/">Tor</a>.</li>
                <li>Consider <a href="https://campaigns.f-secure.com/freedome/sem/en_US/ls">using a VPN</a></li>
                <li>Install <a href="https://www.eff.org/privacybadger">Privacy Badger</a> to block spies and hidden trackers from sites you visit.</li>
            </ol>
        </div>
    </body>
</html>
