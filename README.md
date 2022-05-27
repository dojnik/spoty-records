Fork was created for the purpose of fixing issues with using Extended Spotify Streaming Data.  
This fork is not only getting features as it used to, but it also aquires genres for every track for further analytical purposes.

Be aware that this project is very wonky when it comes to getting A LOT OF DATA sorted out. Spotify API makes it even harder.

/// Initial project README
Extract your extended Spotify streaming history, connect to the Spotify API to acquire the songs' features and genre, and organize everything into a handy .csv file. 

Dependencies:

<ul>
<li>Pandas: https://pandas.pydata.org/</li>
<li>Spotipy: https://spotipy.readthedocs.io/en/2.7.1/</li>
<li>Requests: https://requests.readthedocs.io/en/master/</li>
</ul>

Instructions:

1. Email privacy@spotify.com, that you need your extended streaming data. This process takes a while. In my case it took almost a month to get files.

2. Sign up at Spotify for Developers at https://developer.spotify.com/. Select 'Create an app'. From the app panel, take note of your Client ID and Client Secret. Then select 'Edit settings' and whitelist a link in Redirect URIs. If you don't have a site, http://localhost:7777/callback will do. Take note of this link too.

3. Open config.py and insert your Spotify username, Client ID, Client Secret and Redirect URI. You can leave the scope as is.

4. Execute main.py. If it's the first time, Spotipy will need user authentication. It will try to open a link in your browser, or failing that, will print the link in your console/terminal. Follow the link, log in with your Spotify account, and accept the permissions. Then you will be taken to the Redirect URI. Paste the URI in the console. 

5. The script will now reconstruct your listening history, connect to Spotify API to get the song IDs, and then use those IDs to extract the features. 

5. If you still miss IDs or features, you can run the script again and retry your luck with the API. Collected IDs and features are saved locally, so we don't make repeated requests. 

6. Find your song history, complete with features, in 'output/final.csv'. Happy exploration! 
