---
custom_edit_url: null
sidebar_position: 4
---

![1](https://github.com/Knign/Write-ups/assets/110326359/5a3b3e6d-e168-4a00-a611-63e468d952b9)

Let's click on the `My account` button.

![2](https://github.com/Knign/Write-ups/assets/110326359/0de146f4-dd1c-44d2-ac97-887fbf2688aa)

We are proxying the traffic through Burp Suite.

Therefore we can find the login request in the `Proxy > HTTP History` tab.

![3](https://github.com/Knign/Write-ups/assets/110326359/e68c04c5-9e18-4313-a910-7c2d476cc886)

Let's forward the request to the `Intruder`.

Once in the `Intruder`, let's set the payload field on the `username` parameter.

![4](https://github.com/Knign/Write-ups/assets/110326359/44fa0689-7651-47a4-b9dd-5484078e667c)

Now we have to set the payload type to `Simple list`. Once that is done, we can paste the usernames provided to us here in the `Payloads settings` section.

![5](https://github.com/Knign/Write-ups/assets/110326359/8c850e94-7686-4f9a-807d-5cfdc0fcb8d0)

Next, in the `Intruder > Settings` tab, we have to go to the `Grep - Extract` section and clink on the `Add` button.

![6](https://github.com/Knign/Write-ups/assets/110326359/87814008-4876-4c37-a43d-8dc7d77bc561)

Inside the pop-up, select the following string:
```
Invalid username or password.
```

![7](https://github.com/Knign/Write-ups/assets/110326359/fdb842d3-b803-4335-a6bb-7df509e86b3c)

We can now start the attack.

![8](https://github.com/Knign/Write-ups/assets/110326359/69b16163-a4e8-4b56-ad50-1a3c9728663a)

As we can see, the request with the `username` parameter set to `apps` return a slightly different response, without the full stop.
This means that the username worked which triggered different behaviour.

Now, we have to fuzz the password. With the `username` parameter set to `apps`, add the payload filed to the `password` parameter.

![9](https://github.com/Knign/Write-ups/assets/110326359/861d216b-0f0a-4263-b329-35c99335a663)

In the `Payloads` tab, set the type to `Sin=mple list` and paste the passwords provided to us.

![10](https://github.com/Knign/Write-ups/assets/110326359/c5d943e7-4219-4832-81bf-ef4b5324e862)

Let's start the attack.

![11](https://github.com/Knign/Write-ups/assets/110326359/1e0e5a08-1114-41ee-88b7-64a863200db9)

The request where the `password` parameter was set to `1111` returned a 302 response.

Now we can login using the fuzzed credentials:

| Username | Password |
| -------- | -------- |
| apps         | 1111         |

![12](https://github.com/Knign/Write-ups/assets/110326359/c251bffb-66ea-472c-b1b6-d1c85653ef6e)

We have solved the lab.

![13](https://github.com/Knign/Write-ups/assets/110326359/db936a8f-fc20-4ea7-9f0e-e5d9915075fa)
