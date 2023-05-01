<?php
// check if the search form has been submitted
if (isset($_GET['query'])) {
  // get the search query from the form
  $query = $_GET['query'];

  // search for study materials that match the query
  // (this is just an example - you'll need to implement your own search logic)
  $results = search_study_materials($query);

  // display the search results
  foreach ($results as $result) {
    echo "<p><a href='{$result['file']}'>{$result['title']}</a></p>";
  }
}

// example function to search for study materials (you'll need to implement your own search logic)
function search_study_materials($query) {
  // example data (you'll need to get this data from your database or file system)
  $study_materials = [
    ['title' => 'Mechanics Chapter Gravitation', 'file' => 'math_chapter1.pdf'],
    ['title' => 'Math Chapter 2', 'file' => 'math_chapter2.pdf'],
    ['title' => 'Science Chapter 1', 'file' => 'science_chapter1.pdf'],
    ['title' => 'Science Chapter 2', 'file' => 'science_chapter2.pdf'],
    ['title' => 'History Chapter 1', 'file' => 'history_chapter1.pdf'],
    ['title' => 'History Chapter 2', 'file' => 'history_chapter2.pdf'],
  ];

  // search for study materials that match the query
  $results = [];
  foreach ($study_materials as $material) {
    if (stripos($material['title'], $query) !== false) {
      $results[] = $material;
    }
  }

  return $results;
}
