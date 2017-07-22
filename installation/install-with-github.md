# Install Drone with GitHub

## How to register OAuth application

Go to your GiHub [profile setting](https://github.com/settings/profile) and click `OAuth applications` under `Developer settings` menu on left sidebar.

<img src="images/github-setup-01.png" />

You will see the following register page.

<img src="images/github-setup-02.png" />

Please make sure that your drone `Authorization callback URL` setting. It is very import the authorization callback URL matches your http(s) scheme and hostname exactly with **/authorize** as the path.

<img src="images/github-setup-03.png" />

Copy `Client ID` and `Client Secret`

<img src="images/github-setup-04.png" />

Open your drone home page in your browser and login as Github account.

<img src="images/github-setup-05.png" />
