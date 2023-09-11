# MetaGPT Demonstration

## Description

The `metagpt` demonstration creates a team of Agents that then creates an
application based on a sentence provided at startup. 

The technologies used:

- **[MetaGPT](https://github.com/geekan/MetaGPT)**: Provides the package/library
that brings this all together.

## Installation

Note these installation instructions assume you are running a Fedora Linux 
instance with toolbox installed. For installation on other operating systems, 
follow the steps as executed in the build script.

### Setup the Environment

Use the following command to download this repository:

    git clone https://github.com/break-free/metagpt-demo.git

Once downloaded enter the directory and run the build script. Note you need an 
OpenAI API key to run the build script; it will not run without one.

    cd metagpt-demo
    ./setup/build_metagpt-demo.sh $OPENAI_API_KEY

Once completed, enter the toolbox.

    toolbox enter metagpt-demo

### Download and setup MetaGPT

Exit the current directory and then download MetaGPT

    cd ..
    git clone https://github.com/geekan/MetaGPT.git
    cd MetaGPT

Prior to installing packages, the following changes must be made to the
`requirements.txt` file.

    sed -i 's/.*pygame.*/pygame==2.1.3 /g' requirements.txt
    echo -e '\nhttpx==0.24.1' >> requirements.txt

Use the following commands to install the necessary packages:

    sudo npm install -g @mermaid-js/mermaid-cli
    export PUPPETEER_SKIP_CHROMIUM_DOWNLOAD=true
    sudo python3 setup.py install

## Demonstration

> [!NOTE]
> This command usually results in a playable game but mileage may vary!
> Occasionally, the game will not play and each iteration tends to look
> slightly different.

To run MetaGPT, simply use the following command.

    python3 startup.py "write a cli tic-tac-toe game based on pygame"

Another option is the following.

    python3 startup.py "write a gui snake game based on pygame"

In both cases, to improve the results, add `--code_review True` to the end of
the command.

## Credits

- **MetaGPT Authors**: Thank you for providing a compelling use case for an
autonomous team of Agents!

## License

Refer to [the license](LICENSE).
