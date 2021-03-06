---
path: '/materials/apple-music-js'
type: 'GitHub'
img: './screenshot.png'
material:
  title: 'apple-music-js'
  url: 'https://github.com/tvillarete/apple-music-js'
  github_url: 'https://github.com/tvillarete/apple-music-js'
  subscribers_count: '26'
  stargazers_count: '1366'
  tags: ['']
  subtitle: 'A music streaming service created from the ground up using ReactJS & Redux'
  clone_url: 'https://github.com/tvillarete/apple-music-js.git'
  ssh_url: 'git@github.com:tvillarete/apple-music-js.git'
  pushed_at: '2019-02-05T17:33:56Z'
  updated_at: '2019-02-08T21:04:45Z'
  author:
    name: 'tvillarete'
    avatar: 'https://avatars3.githubusercontent.com/u/21055469?v=4'
    github_url: 'https://github.com/tvillarete'
  latestRelease:
    tag_name: null
    name: null
    url: null
    created_at: null
---
![og](https://user-images.githubusercontent.com/21055469/43682115-2b5a1682-981e-11e8-973d-fe316aa3a49b.png)
---
Built by **Tanner Villarete** 

Connect with me on [LinkedIn](https://linkedin.com/in/tvillarete)! I'll be graduating soon ;)

# How far can JavaScript take us?

Turns out, pretty dang far. This web app was my attempt at mimicking Apple's iOS music app, and I think I've come pretty close! 

Check out a live demo [here](http://tannerv.com/music)

---
![screen shot 2018-08-12 at 9 49 19 am](https://user-images.githubusercontent.com/21055469/44004287-0a541a80-9e15-11e8-93e8-ff3606dd4db1.png)
---
![screen shot 2018-08-12 at 9 49 27 am](https://user-images.githubusercontent.com/21055469/44004289-0df0907e-9e15-11e8-9bcf-ec5e62bcd70a.png)
---
I'm in my fourth year of college, and it's been super cool to see how much I've improved and continue to improve all aspects of programming. 

## Backend API
The API is hosted on a Raspberry Pi, and it's kept private (but still accessible if you try) so that it doesn't get overloaded. If you're interested in building your own backend to plug into this tool, here's what my database and endpoints look like:

### Database
There are six required columns: 
- `name`: The name of the song
- `artist`: The artist name
- `album`: The album name
- `track`: The index of the song relative to the album (To order songs in an album)
- `url`: A URL to the audio file
- `artwork`: A URL to the album artwork image
```mysql
mysql> use music;

Database changed
mysql> desc tracks;
+------------+------------------+------+-----+---------+----------------+
| Field      | Type             | Null | Key | Default | Extra          |
+------------+------------------+------+-----+---------+----------------+
| id         | int(10) unsigned | NO   | PRI | NULL    | auto_increment |
| created_at | timestamp        | YES  |     | NULL    |                |
| updated_at | timestamp        | YES  |     | NULL    |                |
| name       | varchar(255)     | NO   |     | NULL    |                |
| artist     | varchar(255)     | NO   |     | NULL    |                |
| album      | varchar(255)     | NO   |     | NULL    |                |
| track      | int(11)          | NO   |     | NULL    |                |
| url        | varchar(255)     | NO   |     | NULL    |                |
| artwork    | varchar(255)     | NO   |     | NULL    |                |
+------------+------------------+------+-----+---------+----------------+
9 rows in set (0.05 sec)
```

### API Endpoints
The backend is built with PHP using the Laravel ORM. I only needed a few API endpoints to get this working:
- `/albums` - Returns a list of all album names with their corresponding artist
- `/album/{album}` - Returns a list of songs from a specified album
- `/artists` - Returns a list of all artists
- `/artist/{artist}` - Returns a list of all albums from a specific artist

Feel free to reach out if you have questions!
