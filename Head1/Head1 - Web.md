In this challenge, we are given a PHP code:

![](https://hackmd.io/_uploads/H1J5Dd55n.png)

The 2nd if say if the "input_data" variable is not null then then the shell will run the command "curl --head " . $_POST['input_data']" and echo the output of this command. The problem is that if we try to pass value of variable input_data directly into the url bar, we will be stopped by this:

![](https://hackmd.io/_uploads/HJLGKuc9n.png)

It is due to we have '\_' in URL. Therefore, we have to try another approach. 
Here is the idea. We will pass URL in the POST method using cURL to avoid that and change '\_' to "%5f".
 curl -d input_data=%3Bls%20%2F http://45.122.249.68:20018/?input%5fdata=

![](https://hackmd.io/_uploads/HJiP9u95h.png)

As you can see, the file flag_0d7049824be12ca9d7da is there. All we have to do now is cat it.
 curl -d input_data=%3Bcat%20%2Fflag_0d7049824be12ca9d7da
http://45.122.249.68:20018/?input%5fdata=

![](https://hackmd.io/_uploads/HJmhjO9q3.png)

And there it is, the flag is W1{ez_head1_huh}.
 



