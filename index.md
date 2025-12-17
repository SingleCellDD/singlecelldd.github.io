SingleCellDD is a community of scientists in Dresden working on Single-Cell Biology. We organise a monthly discussion round and invite speakers for talks in our single cell seminar series. _Everybody is welcome to join!_

# Mailing List 

Announcements are spread via our [mailing list](https://mailman.zih.tu-dresden.de/groups/listinfo/singlecell), feel free to join!

# Chat room

Outside of meetings, discussions continue in our [Matrix room](https://matrix.to/#/#singlecelldd:tu-dresden.de).

TU Dresden members can join with their ZIH login [here](https://matrix.tu-dresden.de/#/#SingleCellDD:tu-dresden.de). Otherwise, you can create an account [here](https://app.element.io/#/login).

# Meeting dates

We meet on a Wednesday every 4 weeks at 13:00. These are the dates planned for 2025 (location in paranthesis). 

<div id="events-list">
  <!-- Events will be dynamically inserted here as an HTML list -->
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/PapaParse/5.3.0/papaparse.min.js"></script>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    const currentDate = new Date();
    const twoDaysAgo = new Date(currentDate);
    twoDaysAgo.setDate(currentDate.getDate() - 2); // Get the date for 2 days ago

    // Function to format the date as "Feb 12, 2025"
    function formatDate(date) {
      const options = { year: 'numeric', month: 'short', day: 'numeric' };
      return new Intl.DateTimeFormat('en-US', options).format(date);
    }

    // Function to display events as an HTML bullet-point list
    function displayEvents(events) {
      const eventsList = document.getElementById("events-list");
      let htmlList = "<ul>"; // Start the unordered list

      events.forEach(event => {
        const eventDate = new Date(event.Date);
        // Check if the event is within the past 2 days or in the future
        if (eventDate >= twoDaysAgo) {
          const formattedDate = formatDate(eventDate);  // Use the new date format
          htmlList += `<li>${formattedDate} (${event.Location})</li>`; // Add each event as a list item
        }
      });

      htmlList += "</ul>"; // End the unordered list

      // Set the HTML list to the div
      eventsList.innerHTML = htmlList;
    }

    // Fetch and parse the CSV file
    Papa.parse("assets/events.csv", {
      download: true,
      header: true,
      dynamicTyping: true,
      complete: function(results) {
        displayEvents(results.data);
      }
    });
  });
</script>

# Organisers

[Andreas Petzold](https://github.com/andpet0101) ([DRESDEN-concept Genome Center](https://github.com/dcgc-bfx)])  
[Fabian Rost](https://orcid.org/0000-0001-6466-2589) (MPI-CBG)

Contact us, if you have any questions.
