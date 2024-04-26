# Dependencies
* Ruby version : 3.0.1
* Bundler version : 2.2.15

# Prerequisites
1. Execute `ruby bin/setup` to install dependencies.

# Script to execute the program
1. `ruby lib/executer.rb 'task/search.xml'`

# Execute the specs
1. `rspec`

# Brief about program structure
1. I have created three classes/models (`SearchResult`, `Connection`, and `Fare`) based on the `search.xml` element structure.
2. Each class represents the details about the attributes specific to it.
3. I have divided the work-flow in three-part.
* FileParsers (which will fetch the details from `search.xml`)
* Journey classes (`Journey`, `SearchResult`, `Connection`, and `Fare`) to fetch appropriate data and process the details.
* Formatters (which will help us to format the output)
4. Other than that, I have also added the `Executer` class to automate the execution of the program.
5. I have also added class `TimeParser` to convert the time into different formats such as hours, date-time, or find out the difference between times in hours.
6. I have added a separate directory `Log` to save the output in different formats.
7. For now, as per requirement, I have only considered XMLs for parsing and `TXT` for formatting. however, I designed the structure so that I can easily add different parsers and Formatters in the future based on requirements.

# My Assumptions
While writing code, I set few assumptions as below,
1. I have calculated the cheapest fares among all the classes instead of only the Standard class(which might be the cheapest one).
2. For Arrival time and Departure time, I converted the format of times to display it in readable format however, I have not changed the time zone to UTC as mentioned in the description.

# Future Enhancements
1. Current implementation can be extended to add functionality when there are multiple currencies available in Fares and we can convert the other currencies to `GBP` for Rate calculation.
2. Currently I have created `XmlFileParser` to parse `XML` files, but we can add more parsers to parse the data when there are other file formats.
3. Currently I have created `FileFormatter` to format the output in `TXT` files, but we can add more formatters to organise the output in different file formats.
