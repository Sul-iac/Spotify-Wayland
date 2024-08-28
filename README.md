# Flatpak Spotify .desktop config file (Hyprland)

this is a beta script.

This file contains a solution for spotify x11/wayland on Hyprland 
to be working with the Flatpak version. 

When downloading the flatpak version on Arch, spotify seems not working with
Wayland, as it uses x11 librairy. But there is some workarounds.

First, make sure you downloaded the `flatpak` version using the flatpak command
`flatpak install spotify`

Make sure you download the `flathub` version
`Found ref ‘app/com.spotify.Client/x86_64/stable’ in remote ‘flathub’ (system).`

Press Y.

Check if the flatpak version is installed using `flatpak list`. 

Go to the application cache folder. 
You can found it at `.local/share/application`.

Create a file named `spotify-wayland.desktop`. 
It will be our new config file for the app.

Copy-paste the content of the file `spotify-wayland-conf` 
on the repo in the newly created file.

You can now save and refresh the cache with the following command:

`sudo update-desktop-database`.

You'll have two different icone for spotify in the app menu loader. 
Feel free to change the title of your app to make it clearer.

I used `Wspotify Wayland`.
 

# What are the comamnds doing ? 

- `flatpak run`: Executes an application installed via Flatpak.
- `--branch=stable`: Uses the stable branch of the Flatpak application.
- `--socket=wayland`: Connects the application to a Wayland compositor.
- `--arch=x86_64`: Specifies the 64-bit architecture for compatibility.
- `--command=/app/extra/bin/spotify`: Defines the path to the Spotify binary within the Flatpak sandbox.
- `--file-forwarding com.spotify.Client`: Facilitates file forwarding to the Spotify client.
- `--enable-gpu-rasterization`: Activates GPU rasterization for enhanced performance.
- `--enable-zero-copy`: Enables zero-copy techniques to improve memory efficiency and reduce latency.
- `--enable-gpu-compositing`: Uses GPU for compositing layers of the user interface.
- `--enable-native-gpu-memory-buffers`: Utilizes native GPU memory buffers for better video memory management.
- `--enable-oop-rasterization`: Activates out-of-process rasterization for improved performance and stability.
- `--enable-features=UseSkiaRenderer`: Uses Skia for rendering, improving graphical quality and speed.
- `--ozone-platform=wayland`: Sets Ozone to use Wayland as the backend.
- `--disable-gpu-sandbox`: Disables GPU sandboxing, potentially improving performance but reducing security.
- `--enable-features=UseSkiaRenderer,WaylandWindowDecorations`: Enables additional features, including Skia rendering and Wayland window decorations.
- `@@u %U @@`: Placeholders for URL or file arguments passed to the application.
