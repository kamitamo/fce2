---
title: "活動予定表"
layout: page
---

  <head>
    <meta charset='utf-8' />
    <link href='assets/css/fullcalendar/main.css' rel='stylesheet' />
    <script src='assets/javascripts/fullcalendar/main.js'></script>
    <script src='assets/javascripts/fullcalendar/locales/ja.js'></script>
    <script>

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
          googleCalendarId: 'ja.japanese#holiday@group.v.calendar.google.com',
          className: 'event_holiday'
        },
        {
          googleCalendarId: '57kunjloinh68h73hug19l4tjg@group.calendar.google.com'
        }
        ],

        eventClick: function(info) {
             alert('タイトル：' + info.event.title + '\n' + '場所：' + info.event.extendedProps.location + '\n' + '詳細：' + info.event.extendedProps.description );
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
