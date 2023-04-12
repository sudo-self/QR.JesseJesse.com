# QR-Code-Generator-html
## Very Simple QR Code Generator written in html using Google API
 <title>JRs QR Corner</title>
 </head>
  
  <body>
      <div class="container-fluid">
          <div class="text-center">
              
              <!-- Get a Placeholder image initially,
              this will change according to the
              data entered later -->
              <img src=
              "https://chart.googleapis.com/chart?cht=qr&chl=Hello+World&chs=160x160&chld=L|0"
              class="qr-code img-thumbnail img-responsive" />
          </div>
          
          <div class="form-horizontal">
              <div class="form-group">
                  <label class="control-label col-sm-2"
                      for="content">
                  </label>
                  <div class="col-sm-10">
                      
                      <!-- Input box to enter the
                      required data -->
                      <input type="text" size="60"
                      maxlength="60" class="form-control"
                      id="content" placeholder="Type here the exact URL, text, or content then click Generate" />
                  </div>
              </div>
              <div class="form-group">
                  <div class="col-sm-offset-2 col-sm-10">
                      
                      <!-- Button to generate QR Code for
                      the entered data -->
                      <button type="button" class=
                          "btn btn-default" id="generate"><b>
                              GENERATE</b>
                      </button>
                  </div>
              </div>
          </div>
      </div>
      <script src=
          "https://code.jquery.com/jquery-3.5.1.js">
      </script>
      
      <script>
          // Function to HTML encode the text
          // This creates a new hidden element,
          // inserts the given text into it
          // and outputs it out as HTML
          function htmlEncode(value) {
              return $('<div/>').text(value)
              .html();
          }
          
          $(function () {
              
              // Specify an onclick function
              // for the generate button
              $('#generate').click(function () {
                  
                  // Generate the link that would be
                  // used to generate the QR Code
                  // with the given data
                  let finalURL =
                  'https://chart.googleapis.com/chart?cht=qr&chl=' +
                  htmlEncode($('#content').val()) +
                  '&chs=160x160&chld=L|0'
                  
                  // Replace the src of the image with
                  // the QR code image
                  $('.qr-code').attr('src', finalURL);
              });
          });
      </script>
    
  </body>
   </html>
