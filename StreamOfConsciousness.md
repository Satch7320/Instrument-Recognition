# Capstone 3
working with audio data is a pain in the ass
labels:
    there are 7 columns in the labels. There is ALSO a separate csv file that contains metadata about each individual track.
    I think there are 2 approaches: 
        I can identify each note, played on each instrument, to identify instruments.
        I can label each composition to the composer.
    The first approach suffers from conflation -- there are really 2 labels: the note and the instrument. Is it possible to have these mixed labels?
    The second approach is heavily limited: I have 330 tracks, and something like 20 artists, but not all are equally represented.
    That means some artists probably don't have enough data to both train and test on. Besides, can I really train the model with an entire song as one data point?

To identify notes and instruments:
    The labels.csv has an entire table per track. Perhaps I can pull the instrument and note columns from each table, then use the slices of the begin/end timestamps in the table to set them as the labels. As a form of transfer learning, the model 