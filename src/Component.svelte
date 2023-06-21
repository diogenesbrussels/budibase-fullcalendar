<script>
  import { getContext } from "svelte";
  import "@fullcalendar/core/locales-all";
  import FullCalendar from "svelte-fullcalendar";
  import interactionPlugin from "@fullcalendar/interaction";
  import daygridPlugin from "@fullcalendar/daygrid";
  import listPlugin from "@fullcalendar/list";
  import multiMonthPlugin from "@fullcalendar/multimonth";
  import { langs, codeLang } from "./lang";

  export let language;
  export let initialView;
  export let navLinks;
  export let calendarEvent, calendarDate;

  export let headerOptionsLeft, headerOptionsCenter, headerOptionsRight;

  export let eventGroup1, eventGroup2, eventGroup3;

  export let dataProvider1;
  export let mappingTitle1,
    mappingDate1,
    mappingId1,
    allDay1,
    mappingStart1,
    mappingEnd1,
    mappingColor1;

  export let dataProvider2;
  export let mappingTitle2,
    mappingDate2,
    mappingId2,
    allDay2,
    mappingStart2,
    mappingEnd2,
    mappingColor2;

  export let dataProvider3;
  export let mappingTitle3,
    mappingDate3,
    mappingId3,
    allDay3,
    mappingStart3,
    mappingEnd3,
    mappingColor3;

  let eventsList = [];

  if (eventsList.length > 0) {
    eventsList = [];
  }
  if (eventGroup1 && dataProvider1 && dataProvider1.rows) {
    dataProvider1.rows.forEach((event) => {
      let eventColor = mappingColor1 ?? "#313131";
      eventsList.push({
        title: event[mappingTitle1],
        date: event[mappingDate1],
        id: event[mappingId1],
        color: eventColor,
        event: event,
        allDay: allDay1,
        start: event[mappingStart1],
        end: event[mappingEnd1],
      });
    });
  }
  if (eventGroup2 && dataProvider2 && dataProvider2.rows) {
    dataProvider2.rows.forEach((event) => {
      let eventColor = mappingColor2 ?? "#313131";
      eventsList.push({
        title: event[mappingTitle2],
        date: event[mappingDate2],
        id: event[mappingId2],
        color: eventColor,
        event: event,
        allDay: allDay2,
        start: event[mappingStart2],
        end: event[mappingEnd2],
      });
    });
  }
  if (eventGroup3 && dataProvider3 && dataProvider3.rows) {
    dataProvider3.rows.forEach((event) => {
      let eventColor = mappingColor3 ?? "#313131";
      eventsList.push({
        title: event[mappingTitle3],
        date: event[mappingDate3],
        id: event[mappingId3],
        color: eventColor,
        event: event,
        allDay: allDay3,
        start: event[mappingStart3],
        end: event[mappingEnd3],
      });
    });
  }
  //eventsList = eventsList;

  let options = {
    headerToolbar: {
      left: headerOptionsLeft,
      center: headerOptionsCenter,
      right: headerOptionsRight,
    },
    plugins: [daygridPlugin, listPlugin, multiMonthPlugin, interactionPlugin],
    initialView: initialView,
    initialDate: Date.now(),
    locale: language,
    dayMaxEvents: true,
    navLinks: navLinks,
    eventClick: (event) => {
      if (typeof calendarEvent === "function") {
        calendarEvent({
          value: event.event.id,
        });
      }
    },
    dateClick: (event) => {
      if (typeof calendarDate === "function") {
        calendarDate({
          value: event.date,
        });
      }
    },
    events: eventsList,
    eventColor: "#378006",
    ...langs[codeLang(language)],
  };
  const { styleable } = getContext("sdk");
  const component = getContext("component");
</script>

<div use:styleable={$component.styles}>
  <FullCalendar {options} />
</div>
