## Photons interactor

This addon installs and configures photons interactor. This can be used to send animations, create and set scenes and much more all through local web requests with no need for an internet interaction. This makes changes fast and reliable.

In the repository, i have added the configuration required to start and install it as an addon though homeassistant and take no credit for Delficks  amazing work. 

See his project here https://photons.delfick.com/apps/interactor/docker.html

If you want to add buttons to HA to trigger photons, you can use rest_command. Take this example and modify to your needs. The IP should not need to be modified.

Pacman example:
```
rest_command:
  pacman:
    url: 'http://127.0.0.1:6100/v1/lifx/command'
    method: "put"
    payload: '{"command":"animation/start", "args":{"animations": "pacman"}}'
    
```
Or maybe set a scene
```
rest_command:
  my_awesome_scene:
    url: 'http://127.0.0.1:6100/v1/lifx/command'
    method: "put"
    payload: '{"command":"scene_apply", "args":{"uuid": "uuid_of_my_awesome_scene"}}'
```

###### Icon by [Icons8](https://icons8.com/icon/YScTDpKhMxMC/smart-home-automation)
