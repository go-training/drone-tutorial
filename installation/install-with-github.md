# Install Drone with GitHub

See the online documentaion: [Single Machine](https://docs.drone.io/installation/github/single-machine/) | [Multi-Machine](https://docs.drone.io/installation/github/multi-machine/) | [Kubernetes](https://docs.drone.io/installation/github/kubernetes/)

## How to register OAuth application

Go to your GiHub [profile setting](https://github.com/settings/profile) and click `OAuth applications` under `Developer settings` menu on left sidebar.

![github-setup-01](images/github-setup-01.png)

You will see the following register page.

![github-setup-02](images/github-setup-02.png)

Please make sure that your drone `Authorization callback URL` setting. It is very import the authorization callback URL matches your http(s) scheme and hostname exactly with **/authorize** (0.8) **/login** (1.0) as the path.

![github-setup-03](images/github-setup-03.png)>

Copy `Client ID` and `Client Secret`

![github-setup-04](images/github-setup-04.png)

Open your drone home page in your browser and login as Github account.

![github-setup-05](images/github-setup-05.png)
