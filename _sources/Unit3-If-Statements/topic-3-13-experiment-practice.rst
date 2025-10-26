.. qnum::
   :prefix: exp-4-
   :start: 1

Practice Problems
============================


.. raw:: html

    <h3>loading...</h3>

    <script type="text/javascript">

      
      function getCookie(cname) {
         let name = cname + "=";
         let decodedCookie = decodeURIComponent(document.cookie);
         let ca = decodedCookie.split(';');
         for(let i = 0; i < ca.length; i++) {
            let c = ca[i];
            while (c.charAt(0) == ' ') {
               c = c.substring(1);
            }
            if (c.indexOf(name) == 0) {
               return c.substring(name.length, c.length);
            }
         }
         return "";
      }

      /*function setCookie(cname, cvalue) {
         document.cookie = cname + "=" + cvalue + ";path=/;SameSite=Lax";
      }*/
         function setCookieBothPaths(cname, cvalue) {
         document.cookie = cname + "=" + cvalue + ";path=/;SameSite=Lax";
         var here = location.pathname.substring(0, location.pathname.lastIndexOf('/') + 1);
         document.cookie = cname + "=" + cvalue + ";path=" + here + ";SameSite=Lax";
      }

      function deleteCookieBothPaths(cname) {
         var past = "Thu, 01 Jan 1970 00:00:00 GMT";
         document.cookie = cname + "=; expires=" + past + ";path=/";
         var here = location.pathname.substring(0, location.pathname.lastIndexOf('/') + 1);
         document.cookie = cname + "=; expires=" + past + ";path=" + here;
      }

      window.onload = function() {

         //a = document.getElementById("hparsons_lg_sql_practice")
         var href = '';
         // get prev set cookie
         var EXP_COOKIE = 'hparsons_lg_sql_221115'
         var cond = getCookie(EXP_COOKIE);
         // not using cookie here; random assignment
         //var cond = '';
         // if no prev set cookie: generate random condition and set cookie
         if (cond != 'wr' && cond != 'hp') {
            var v = Math.floor(Math.random() * 2);
            if (v < 1) {
                cond = 'wr';
            } else {
                cond = 'hp';
            }
            setCookieBothPaths(EXP_COOKIE, cond);
         }

         if (cond == 'wr') {
            href = "topic-3-13-experiment-practice-W.html"
         } else if (cond == 'hp') {
            href = "topic-3-13-experiment-practice-P.html"
         }
         window.location.replace(href);
      };
    </script>

.. raw:: html

    <p>
      Click on the following link to take the post test:
      <b>
        <a href="topic-3-13-experiment-posttest.html">
          <font size="+1">Post test</font>
        </a>
      </b>
    </p>