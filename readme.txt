Overall approach:
We began by making structures for Header, Question, and Answer.  
Then we proceeded to parse out the port if one is included.
The next step was to construct the header and the question.
We wrote a helper function to convert the host into dns format.
Once everything was put together, we sent the packet.
After that we wait to receive a response from the server.
Then we copied the header data into memory and parsed through it,
shifting bits in the packet to get each chunk of data that we needed
and putting them into arrays. Once all the data was collected from
the array and we reached the end of the packet we printed out the
results of the array for the program output.

The main challenge we faced in the milestone was a segment fault
caused by our parsing of arguments, specifically the @ symbol in
front of the IP address which took up a lot of debugging time. 
We struggled with finding the best way to store and construct the 
packet so that the order of the hex dump was correct. We had to
restructure the fields of the header to match the endianness.

For the second half of the project the main challenge was getting
started copying the the header into memory and being able to fiddle
the bits so that we could parse through the packet. It was difficult
to find out how many bits to shift by and how big the indexes should
be but by following the our structs we figured it out. We also had a
bug that took a very long time to find where we were setting the default
port to htons(53) rather than 53 even though our code calls htons later
and it was causing the tests to fail.

We ran our own tests by adding them to the test script at the end because
input redirection didn't work from our own test file. We had to run the
tests manually to see their output.

The features that we are proud of in this project are just generally the
efficient design we took. The code was surprisingly short and even though 
the 2nd half has a lot of bit fiddling that is hard to read, we were able
to pick a structure and work with it well. We also attempted the extra
credit but were not able to finish.




