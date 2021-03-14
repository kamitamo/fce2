---
title: "活動予定表"
layout: page
---

  <head>
    <meta charset='utf-8' />
    <meta name=”robots” content=”noindex”>
    <link href='assets/css/fullcalendar/main.css' rel='stylesheet' />
    <script src='assets/javascripts/fullcalendar/main.js'></script>
    <script src='assets/javascripts/fullcalendar/locales/ja.js'></script>
    <script>

        function AutoLink(str) {
            var regexp_url = /((h?)(ttps?:\/\/[a-zA-Z0-9.\-_@:/~?%&;=+#',()*!]+))/g; // ']))/;
            var regexp_makeLink = function(all, url, h, href) {
                return '<a href="h' + href + '">' + url + '</a>';
            }
            return str.replace(regexp_url, regexp_makeLink);
        }


      document.addEventListener('DOMContentLoaded', function() {
      var calendarEl = document.getElementById('calendar');

      let calendar = new FullCalendar.Calendar(calendarEl, {

      contentHeight: 'auto',
      initialView: 'listMonth',
      themeSystem: 'bootstrap',
      locale: 'ja',
      dayCellContent: function(e) {
        e.dayNumberText = e.dayNumberText.replace('日', '');
      },

      headerToolbar: {
        left: "prev",
        center: "title",
        right: "next"
      },

      
      buttonText: {
        next: '>',
        prev: '<'
      },

      views: {
        listMonth: {
          listDayFormat: { day: 'numeric', weekday: 'narrow' },
          listDaySideFormat: false
        }
      },

      navLinks: false,
      businessHours: true,
      editable: false,


        googleCalendarApiKey: 'AIzaSyAbxROeLBWbK9xs7VGm26Ql2JjpU2VONu0',
        eventSources: [
        {
          googleCalendarId: '57kunjloinh68h73hug19l4tjg@group.calendar.google.com'
        }
        ],

        eventClick: function(info) {
          let location = "";
          let description = "";
          if ( info.event.extendedProps.location !== undefined ) {
               location = info.event.extendedProps.location;
          }
          if ( info.event.extendedProps.description !== undefined ) {
               description = info.event.extendedProps.description;
          }
          alert('件名：' + info.event.title + '\n' + '場所：' + location + '\n' + '詳細：' + description );
          info.jsEvent.preventDefault();
         if (info.event.url) {
         }
        },


      });

        calendar.render();
      });

    </script>
  </head>
  <body>
    <div id='calendar'></div>
  </body>
