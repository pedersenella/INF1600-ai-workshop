---
title: 'ViT: Image Classifier'
colorFrom: indigo
colorTo: indigo
sdk: gradio
app_port: 7860
emoji: 🔥
pinned: false
license: mit
app_file: app.py
---


# INF-1600 AI Deployment workshop

This workshop was developed for the _"Intro to Artificial Intelligence"_ course with
code INF-1600 at UiT: The Arctic University of Norway.

The workshop was a collaboration with UiT and Sopra Steria.

In this workshop, you will get hands on experience with:
* Cloning and pushing code from/to [GitHub](https://github.com).
* Loading and running a pretrained image classification model from [Transformers](https://pypi.org/project/transformers/).
* Developing a simple web application to enable users to test a pretrained model using [Gradio](https://pypi.org/project/gradio/).
* Making a public web app anyone can access using [Hugging Face Spaces](https://huggingface.co/spaces).
* Automizing tasks using [GitHub Actions](https://github.com/features/actions).

And of course, all of this completely **_FOR FREE_**!

## Getting Started

1. Make your first GitHub account by going [here](https://github.com/) and signing up (see top right of website).

2. After logging in to your account on GitHub, go to the code repository [here](https://github.com/andreped/INF1600-ai-workshop).

3. Make a copy of the repository by making a fork (click the `fork` button, choose your user as `owner` and click `create fork`).

4. Now you are ready to clone your own fork to a laptop by opening a terminal and running (remember to replace `<username>` with your own GitHub user name):
```
git clone git+https://github.com/<username>/INF1600-ai-workshop.git
```

5. After cloning, go inside the repository, and from the terminal run these lines to create a virtual environment and activate it:
```
virtualenv -ppython3 venv --clear
source venv/bin/activate
```

On Windows, to activate the virtual environment, run `./venv/Scripts/activate` instead of the `source` command.

6. Install dependencies to the virtual environment by:
```
pip install -r requirements.txt
```

7. To test if everything is working, try to run the following command to launch the web server:
```
python3 app.py
```

8. You can then access the web app by going to [http://127.0.0.1:7860](http://127.0.0.1:7860) in your favourite web browser.

9. From the prompted website, try clicking one of the image examples and clicking the orange `Submit` button. The model results should show on the right after a few seconds.

10. Try accessing this address from your mobile phone.

11. This should not work, to access the app from a different device, you need to serve it.
Try setting `share=True` in the `interface.launch()` call in the `app.py` script.
When running `app.py` now, you should be given a different web address. Try using that one instead on your mobile device.

But of course, hosting the app yourself from your laptop is not ideal. What if there was some alternative way to do this without using your own device **completely for free**...

12. Click [here](https://huggingface.co/join) to go to the Hugging Face sign up page and make an account.

13. After making an account and logging in, click the `+ New` button on the left of the website and choose `Space` from the dropdown.

14. In the `Create a new Space` tab, choose a `Space name` for the app, choose a License (preferably `MIT`), among the `Space SDKs` choose `Gradio`, and finally, click `Create Space`.

We are now given the option to manually add the relevant files, but that is boring... Let's instead try to setup a robot that does that for us!

15. From the Hugging Face website [here](https://huggingface.co), click on your user badge (top right), and from the dropdown clik `Settings`.
On the left hand side of `Settings` site, click `Access Tokens`, and then click `New Token`.
Set the name `HF_TOKEN`, set permissions to `write`, and click `Generate a token`.

16. On your laptop, open the file located at `.github/workflows/deploy.yml`, and at the last line, replace the phrase `andreped/ViT-ImageClassifier` with your own
Hugging Face user and space name.

17. Setup communication with GitHub and Hugging Face by running the follow in the terminal (replace `andreped/ViT-ImageClassifier` like in step 16):
```
git remote add space https://huggingface.co/spaces/andreped/ViT-ImageClassifier
```

18. Then push the code to GitHub by running:
```
git push --force space main
```

19. Now go to your GitHub fork (e.g., `https://github.com/<username>/INF1600-ai-workshop/`) and verify that the code is there.

20. Then click the `Actions` tab to see running workflows. Verify that the workflow ran successfully by clicking the current run and checking workflow status.

21. Finally, we can then head over to our Hugging Face space and check if everything is working. My own app is hosted at [https://huggingface.co/spaces/andreped/ViT-ImageClassifier](https://huggingface.co/spaces/andreped/ViT-ImageClassifier)

## Workshop Organizers

* [André Pedersen](https://github.com/andreped), Apps, Sopra Steria
* [Tor-Arne Schmidt Nordmo](https://uit.no/ansatte/person?p_document_id=581687), IFI, UiT: The Arctic University of Norway

## License

The code in this repository is released under [MIT license](https://github.com/andreped/INF1600-ai-workshop).
