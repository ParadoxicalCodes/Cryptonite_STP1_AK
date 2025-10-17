# Challenge Description
Additional details will be available after launching your challenge instance.

After launching we are given a website in which we have to find the flag.
# Thought Process & Solution
<img width="724" height="509" alt="image" src="https://github.com/user-attachments/assets/1303de59-ffe4-44a6-871a-4a222c29b873" />

Opening up the site leads to this webpage. Since the challenge title mentions burp it likely means we have to investigate and manipulate requests that a webpage makes to get our flag.
So I have burp running with proxy mode on - this would allow me to inspeact and see clearly what exactly a webpage sends to server to communicate and generate responses accordingly.

<img width="1493" height="804" alt="image" src="https://github.com/user-attachments/assets/51f4efa5-aaea-42a2-aa7b-32c49d990cf9" />

In burp we see some details about the request made by the website
  - like its a POST request
  - host is our picoctf instance
  - user-agent parameter tells us about the browser that is initiating this request ?
  - content length tells us the size request being sent in bytes

After forwarding the request we see that the site generates another request

<img width="1538" height="738" alt="image" src="https://github.com/user-attachments/assets/013bc328-cc5c-48d0-b03b-847e664393a5" />

This one tells us that
  - h

Which leads to opening of this webpage

<img width="1387" height="816" alt="image" src="https://github.com/user-attachments/assets/0766d7eb-8f1c-4657-a4b2-9c650d49fa36" />

And putting in some value of otp results in "Invalid OTP"

<img width="577" height="515" alt="image" src="https://github.com/user-attachments/assets/7834e686-3dea-4541-a8b7-2aa2429ce1ba" />


So now that we have some pre eliminary understanding of the site and how it works, two methods strike me here:
  - either i have to trick the site to open a document that it doesnt intend to normally -> this means manipulate the POST request content
  - or get admin access since i see the space for password and id -> this would mean SQL injection



**Flag:** `pwn.college{}`
## New Learning
## Reference
