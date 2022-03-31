# Block bad bots with nginx

Battle tested, can handle ~40k requests a second without problem if you have a decent server.

![Screenshot of RPS](https://i.breached.co/0EDI9QySCpPjh4ya.png)

```
Specs of the server I used during testing (If you're curious):
CPU: AMD Ryzen 9 3900X (8 CPU Cores @ 3.9Ghz+)
RAM: 32GB DDR4 RAM
```

How to use:
1) Download the block.map file into your /etc/nginx/ folder.
2) Edit /etc/nginx/nginx.conf and add "map_hash_bucket_size 256;" in the http block (Example of how it should look [here](https://i.breached.co/oDLMk9feqnqnLrSW.png)).
3) Add "include /etc/nginx/block.map;" to the first line of your nginx website config file. (See nginx-config.example.conf if you're confused).
4) Restart nginx.


Contributions are more than welcome. Just state what the added filters are indended to block. 
