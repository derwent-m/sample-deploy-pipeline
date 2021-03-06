# Building the pipeline

From the side menu select `New item`.

<img src="images/building-the-pipeline-new-item-link.png" width="600"/>

Enter the name `sample-flask-app` for the project, select `Freestyle project` and click `OK`.

<img src="images/building-the-pipeline-new-item.png" width="600"/>

Under the heading `Source Code Management`, select the `Git` radio button.

Enter the URL of your fork of the `sample-flask-app` repository. e.g. `https://github.com/wilvk/sample-flask-app`

<img src="images/building-the-pipeline-source-code-management.png" width="600"/>

Under the heading `Build` select `Add build step` and then select `Execute shell`.

<img src="images/building-the-pipeline-build-step.png" width="600"/>

In the `Command` textbox enter the following:

```sh
docker-compose down
docker-compose up --detach --build
sleep 30
docker-compose logs
```

_(Note: if the build fails in the following steps, try increasing the sleep wait to 60 seconds or more)_

Then select `Save`.

<img src="images/building-the-pipeline-save.png" width="600"/>

Then from the job task list, select `Build Now`.

Your app should now be building. It should take up to a minute or so to complete.

<img src="images/building-the-pipeline-history.png" width="600"/>

Once the build has completed, browse to [localhost:8000](http://localhost:8000) to see your app.

<img src="images/building-the-pipeline-sample-flask-app.png" width="600"/>
