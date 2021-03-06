---
layout: default
title: Events
stylesheets: ["https://cdn.datatables.net/1.10.20/css/dataTables.bootstrap4.min.css"]
scripts: [
  "https://cdn.datatables.net/1.10.20/js/jquery.dataTables.min.js",
  'https://cdn.datatables.net/1.10.20/js/dataTables.bootstrap4.min.js',
  "assets/js/events.js",
]
---

## SIGLEX events

SIGLEX maintains a list of events (conferences and workshops) as having special interest to SIGLEX members.
You can search this list below.
You can also suggest an event to be added to this list by creating a pull request at [the SIGLEX website repository](https://github.com/acl-org/siglex/).

Proceedings of many of these workshops and conferences can be found at the [ACL SIGLEX anthology](https://www.aclweb.org/anthology/sigs/siglex/).

<table id="events" class="table table-striped table-bordered" style="width:100%">
  <thead>
    <tr>
      <th>Event Date</th>
      <th>Submission Date</th>
      <th>Event</th>
      <th>Location</th>
      <th>Details</th>
    </tr>
    <tr>
      <th><input type="text" placeholder="Search" /></th>
      <th><input type="text" placeholder="Search" /></th>
      <th><input type="text" placeholder="Search" /></th>
      <th><input type="text" placeholder="Search" /></th>
      <th><input type="text" placeholder="Search" /></th>
    </tr>
  </thead>
  <tbody>
    {% for post in site.categories.event %}
    <tr>
      <td style="white-space: nowrap;">{{ post.date | date: "%Y-%m-%d" }}</td>
      <td style="white-space: nowrap;">{% if post.event_submission_date %}{{ post.event_submission_date | date: "%Y-%m-%d" }}{% endif %}</td>
      <td><a href="{{ post.event_url }}">{{ post.event_name }}</a></td>
      <td>{{ post.event_location }}</td>
      <td><a href="{{ site.baseurl }}{{ post.url }}">Details</a></td>
    </tr>
    {% endfor %}
  </tbody>
</table>
