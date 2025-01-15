# How-I-Tame-Scary-Data-with-Power-Query

Have you ever worked with "scary data"? You know that kind of data pulled straight from the web, riddled with long, intimidating URLs packed with IDs, parameters, and cryptic structures? Or datasets like survey responses, social media data, CRM or ERP exports. 

It can feel overwhelming at first, but you’ll be happy to know that most of the fields in these types of datasets are typically riddled with irrelevant metadata, duplicate entries and inconsistent formats. However, thanks to Power Query, I can clean, reshape, and extract the gems hidden in the mess.

###### *Sample 1*
![image](https://github.com/user-attachments/assets/ae8606e3-9e7f-46de-8984-d334d3c7f309)

###### *Sample 2* 
![image](https://github.com/user-attachments/assets/ba3df96e-3cf0-4990-9ce8-ec65f6ea3ce6)


I’ll share a simple approach I use to transform these daunting datasets into clean, usable formats.

#### The Problem: Scary Data from Web API

When working with web data or APIs, I usually encounter URLs like this: *“http://environment.data.gov.uk/flood-monitoring/id/floods/034WAB42428176”*

At first glance, it was difficult to make sense of what was relevant. But I realised I only needed the ID after "floods/"? This is where Power Query comes to the rescue.

Here’s how I clean and organise such data:

#### - Load the Data

I start by loading the dataset into Power Query using the web connector. For this example, I extracted the data from a public API (Environment Agency), which didn’t require authentication or an API key.

#### - Extract the Relevant Information

To isolate the ID from the URL, I use the Text.AfterDelimiter function. This function lets me pull out everything after a specific text. 

Here’s the formula I apply in a custom column: *Text.AfterDelimiter([ColumnName], "floods/")* OR highlight the column, *Transform tab > Extract > Text After Delimiter* , then enter “floods/”. This simple step instantly transforms a long, scary URL into just the ID I need.

#### -Remove Unnecessary Metadata Columns

Columns containing file information are often irrelevant for analysis and can clutter the dataset, making it appear bulky and disorganised. Removing them can significantly improve the dataset's clarity.

#### - Validate and Format
I validate the data to ensure there are no errors or inconsistencies. If needed, I clean up leading or trailing spaces, change the data type, or add additional transformations.

#### - Document and Save

Power Query’s step-by-step approach makes it easy to document every transformation I apply. This ensures transparency and makes it simple to replicate the process in the future.

###### *After transformation*
![image](https://github.com/user-attachments/assets/2b1e29c8-e6d8-44bc-8d8d-415fc41cb5ac)


![image](https://github.com/user-attachments/assets/cff3bf2e-fa44-4582-8f17-4f5775519db4)

With Power Query, I can break datasets down into manageable pieces, extract what I need for analysis, and turn the mess into meaningful insights.
