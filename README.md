# Flatpak Spotify .desktop config file (Hyprland)

This file contains a solution for spotify x11/wayland on Hyprland to be working with the Flatpak version. 

When downloading the flatpak version on Arch, spotify seems not working with
Wayland, as it uses x11 librairy. But there is some workarounds.

First, make sure you downloaded the `flatpak` version using the flatpak command
`flatpak install spotify`

Mkae sure you download the `flathub` version
`Found ref ‘app/com.spotify.Client/x86_64/stable’ in remote ‘flathub’ (system).`

And press Y.

Check if the flatpak version is installed using `flatpak list`. 

Go to the application cache folder. You can found it at `.local/share/application`.

Create a file named `spotify-wayland.desktop`. It will be our new config file for the app.

Copy-paste the content of the file `spotify-wayland-conf` on the repo in the newly created file.

You can now save and refresh the cache with the following command:

`sudo update-desktop-database`.

You'll have two different icone for spotify in the app menu loader. 
Feel free to change the title of your app to make it clearer.

I used `Wspotify Wayland`.
 


