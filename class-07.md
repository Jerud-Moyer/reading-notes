## The past, present and future of local storage for web apps

- Diving in
    - web apps need localStorage
    - cookies can be used but have downsides
        - slow down
        - unencrypted
        - limited to about 4 kb
    - what we want
        - more storage
        - on the client
        - persists beyond page refresh
        = isn't transmitted to server
    -  hacks before HTML5
        - browser specific or 3rd party plugins
- Introducing HTML% storage
    - or *web storage*
    - most browsers support now
    - store key value pairs locally
- using HTML5 storage
    - store data based on a named key, then retrieve that data with same named key
    - setItem will overwrite previous data (same name key)
    - getItem with noexisten key will return null
- tracking changes to storage area
    - trap data storage event
    - 