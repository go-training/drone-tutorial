# Install Drone with GitLab

See the online documentaion: [Single Machine](https://docs.drone.io/installation/gitlab/single-machine/) | [Multi-Machine](https://docs.drone.io/installation/gitlab/multi-machine/)

## How to register OAuth application

Go to your GitLab [profile setting](https://gitlab.com/profile) and navigate to your account settings and choose `Applications` from the menu.

![gitlab-setup-01](images/gitlab-setup-01.png)

Please make sure that your drone `Redirect URI` setting. It is very import the authorization callback URL matches your http(s) scheme and hostname exactly with **/authorize** (0.8) **/login** (1.0) as the path.

![gitlab-setup-02](images/gitlab-setup-02.png)

Copy `Application ID` and `Secret`

![gitlab-setup-03](images/gitlab-setup-03.png)

Open your drone home page in your browser and login as gitlab account.

![gitlab-setup-04](images/gitlab-setup-04.png)
