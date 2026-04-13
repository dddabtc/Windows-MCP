[![MseeP.ai Security Assessment Badge](https://mseep.net/pr/cursortouch-windows-mcp-badge.png)](https://mseep.ai/app/cursortouch-windows-mcp)

<div align="center">
  <h1>🪟 Windows-MCP</h1>

  <a href="https://github.com/CursorTouch/Windows-MCP/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-green" alt="License">
  </a>
  <img src="https://img.shields.io/badge/python-3.13%2B-blue" alt="Python">
  <img src="https://img.shields.io/badge/platform-Windows%207–11-blue" alt="Platform: Windows 7 to 11">
  <img src="https://img.shields.io/github/last-commit/CursorTouch/Windows-MCP" alt="Last Commit">
  <br>
  <a href="https://x.com/CursorTouch">
    <img src="https://img.shields.io/badge/follow-%40CursorTouch-1DA1F2?logo=twitter&style=flat" alt="Follow on Twitter">
  </a>
  <a href="https://discord.com/invite/Aue9Yj2VzS">
    <img src="https://img.shields.io/badge/Join%20on-Discord-5865F2?logo=discord&logoColor=white&style=flat" alt="Join us on Discord">
  </a>

</div>

<br>

**Windows MCP** is a lightweight, open-source project that enables seamless integration between AI agents and the Windows operating system. Acting as an MCP server bridges the gap between LLMs and the Windows operating system, allowing agents to perform tasks such as **file navigation, application control, UI interaction, QA testing,** and more.

mcp-name: io.github.CursorTouch/Windows-MCP

## Updates
- Windows-MCP reached `1M+ Users` in [Claude Desktop Extensiosn](https://claude.ai/directory). 
- Windows-MCP is now available on [PyPI](https://pypi.org/project/windows-mcp/) (thus supports `uvx windows-mcp`)
- Windows-MCP is added to [MCP Registry](https://github.com/modelcontextprotocol/registry)
- Try out 🪟[Windows-Use](https://github.com/CursorTouch/Windows-Use)!!, an agent built using Windows-MCP.
- Windows-MCP is now featured as Desktop Extension in `Claude Desktop`.

### Supported Operating Systems

- Windows 7
- Windows 8, 8.1
- Windows 10
- Windows 11  

## 🎥 Demos

<https://github.com/user-attachments/assets/d0e7ed1d-6189-4de6-838a-5ef8e1cad54e>

<https://github.com/user-attachments/assets/d2b372dc-8d00-4d71-9677-4c64f5987485>

## ✨ Key Features

- **Seamless Windows Integration**  
  Interacts natively with Windows UI elements, opens apps, controls windows, simulates user input, and more.

- **Use Any LLM (Vision Optional)**
   Unlike many automation tools, Windows MCP doesn't rely on any traditional computer vision techniques or specific fine-tuned models; it works with any LLMs, reducing complexity and setup time.

- **Rich Toolset for UI Automation**  
  Includes tools for basic keyboard, mouse operation and capturing window/UI state.

- **Lightweight & Open-Source**  
  Minimal dependencies and easy setup with full source code available under MIT license.

- **Customizable & Extendable**  
  Easily adapt or extend tools to suit your unique automation or AI integration needs.

- **Real-Time Interaction**  
  Typical latency between actions (e.g., from one mouse click to the next) ranges from **0.2 to 0.9 secs**, and may slightly vary based on the number of active applications and system load, also the inferencing speed of the llm.

- **DOM Mode for Browser Automation**  
  Special `use_dom=True` mode for State-Tool that focuses exclusively on web page content, filtering out browser UI elements for cleaner, more efficient web automation.

## 🛠️Installation

**Note:** When you install this MCP server for the first time it may take a minute or two because of installing the dependencies in `pyproject.toml`. In the first run the server may timeout ignore it and restart it.

### Prerequisites

- Python 3.13+
- UV (Package Manager) from Astra, install with `pip install uv` or `curl -LsSf https://astral.sh/uv/install.sh | sh`
- `English` as the default language in Windows highly preferred or disable the `App-Tool` in the MCP Server for Windows with other languages.

<details>
  <summary>Install in Claude Desktop</summary>

  1. Install [Claude Desktop](https://claude.ai/download) and

```shell
npm install -g @anthropic-ai/mcpb
```


  2. Configure the extension:

  **Option A: Install from PyPI (Recommended)**
  
  Use `uvx` to run the latest version directly from PyPI.

  Add this to your `claude_desktop_config.json`:
  ```json
  {
    "mcpServers": {
      "windows-mcp": {
        "command": "uvx",
        "args": [
          "windows-mcp"
        ]
      }
    }
  }
  ```

  **Option B: Install from Source**

  1. Clone the repository:
  ```shell
  git clone https://github.com/CursorTouch/Windows-MCP.git
  cd Windows-MCP
  ```

  2. Add this to your `claude_desktop_config.json`:
  ```json
  {
    "mcpServers": {
      "windows-mcp": {
        "command": "uv",
        "args": [
          "--directory",
          "<path to the windows-mcp directory>",
          "run",
          "windows-mcp"
        ]
      }
    }
  }
  ```



  3. Open Claude Desktop and enjoy! 🥳


  5. Enjoy 🥳.

For additional Claude Desktop integration troubleshooting, see the [MCP documentation](https://modelcontextprotocol.io/quickstart/server#claude-for-desktop-integration-issues). The documentation includes helpful tips for checking logs and resolving common issues.
</details>

<details>
  <summary>Install in Perplexity Desktop</summary>

  1. Install [Perplexity Desktop](https://apps.microsoft.com/detail/xp8jnqfbqh6pvf):

  2. Clone the repository.

```shell
git clone https://github.com/CursorTouch/Windows-MCP.git

cd Windows-MCP
```
  
  3. Open Perplexity Desktop:

Go to `Settings->Connectors->Add Connector->Advanced`

  4. Enter the name as `Windows-MCP`, then paste the following JSON in the text area.


  **Option A: Install from PyPI (Recommended)**

  ```json
  {
    "command": "uvx",
    "args": [
      "windows-mcp"
    ]
  }
  ```

  **Option B: Install from Source**

  ```json
  {
    "command": "uv",
    "args": [
      "--directory",
      "<path to the windows-mcp directory>",
      "run",
      "windows-mcp"
    ]
  }
  ```


5. Click `Save` and Enjoy 🥳.

For additional Claude Desktop integration troubleshooting, see the [Perplexity MCP Support](https://www.perplexity.ai/help-center/en/articles/11502712-local-and-remote-mcps-for-perplexity). The documentation includes helpful tips for checking logs and resolving common issues.
</details>

<details>
  <summary> Install in Gemini CLI</summary>

  1. Install Gemini CLI:

```shell
npm install -g @google/gemini-cli
```


  2. Configure the server in `%USERPROFILE%/.gemini/settings.json`:


  3. Navigate to `%USERPROFILE%/.gemini` in File Explorer and open `settings.json`.

  4. Add the `windows-mcp` config in the `settings.json` and save it.

```json
{
  "theme": "Default",
  ...
  "mcpServers": {
    "windows-mcp": {
      "command": "uvx",
      "args": [
        "windows-mcp"
      ]
    }
  }
}
```
*Note: To run from source, replace the command with `uv` and args with `["--directory", "<path>", "run", "windows-mcp"]`.*


  5. Rerun Gemini CLI in terminal. Enjoy 🥳
</details>

<details>
  <summary>Install in Qwen Code</summary>
  1. Install Qwen Code:

```shell
npm install -g @qwen-code/qwen-code@latest
```

   2. Configure the server in `%USERPROFILE%/.qwen/settings.json`:


  3. Navigate to `%USERPROFILE%/.qwen/settings.json`.

  4. Add the `windows-mcp` config in the `settings.json` and save it.

```json
{
  "mcpServers": {
    "windows-mcp": {
      "command": "uvx",
      "args": [
        "windows-mcp"
      ]
    }
  }
}
```
*Note: To run from source, replace the command with `uv` and args with `["--directory", "<path>", "run", "windows-mcp"]`.*


  5. Rerun Qwen Code in terminal. Enjoy 🥳
</details>

<details>
  <summary>Install in Codex CLI</summary>
  1. Install Codex CLI:

```shell
npm install -g @openai/codex
```

  2. Configure the server in `%USERPROFILE%/.codex/config.toml`:

  3. Navigate to `%USERPROFILE%/.codex/config.toml`.

  4. Add the `windows-mcp` config in the `config.toml` and save it.

```toml
[mcp_servers.windows-mcp]
command="uvx"
args=[
  "windows-mcp"
]
```
*Note: To run from source, replace the command with `uv` and args with `["--directory", "<path>", "run", "windows-mcp"]`.*


  5. Rerun Codex CLI in terminal. Enjoy 🥳
</details>

---

## 🔨MCP Tools

MCP Client can access the following tools to interact with Windows:

- `Click`: Click on the screen at the given coordinates.
- `Type`: Type text on an element (optionally clears existing text).
- `Scroll`: Scroll vertically or horizontally on the window or specific regions.
- `Move`: Move mouse pointer or drag (set drag=True) to coordinates.
- `Shortcut`: Press keyboard shortcuts (`Ctrl+c`, `Alt+Tab`, etc).
- `Wait`: Pause for a defined duration.
- `Snapshot`: Combined snapshot of default language, browser, active apps and interactive, textual and scrollable elements along with screenshot of the desktop. Supports `use_dom=True` for browser content extraction (web page elements only) and `use_vision=True` for including screenshots.
- `App`: To launch an application from the start menu, resize or move the window and switch between apps.
- `Shell`: To execute PowerShell commands.
- `Scrape`: To scrape the entire webpage for information.
- `PlaySound`: Play a WAV audio file (default: Windows notify sound). Supports async playback, looping, and stopping.

## 🤝 Connect with Us
Stay updated and join our community:

- 📢 Follow us on [X](https://x.com/CursorTouch) for the latest news and updates

- 💬 Join our [Discord Community](https://discord.com/invite/Aue9Yj2VzS)

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=CursorTouch/Windows-MCP&type=Date)](https://www.star-history.com/#CursorTouch/Windows-MCP&Date)

## 👥 Contributors

Thanks to all the amazing people who have contributed to Windows-MCP! 🎉

<a href="https://github.com/CursorTouch/Windows-MCP/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=CursorTouch/Windows-MCP" />
</a>

We appreciate every contribution, whether it's code, documentation, bug reports, or feature suggestions. Want to contribute? Check out our [Contributing Guidelines](CONTRIBUTING)!

## 🔒 Security

**Important**: Windows-MCP operates with full system access and can perform irreversible operations. Please review our comprehensive security guidelines before deployment.

For detailed security information, including:
- Tool-specific risk assessments
- Deployment recommendations
- Vulnerability reporting procedures
- Compliance and auditing guidelines

Please read our [Security Policy](SECURITY.md).

## 📊 Telemetry

Windows-MCP collects usage data to help improve the MCP server. No personal information, no tool arguments, no outputs are tracked.

To disable telemetry, add the following to your MCP client configuration:

```json
{
  "mcpServers": {
    "windows-mcp": {
      "command": "uvx",
      "args": [
        "windows-mcp"
      ],
      "env": {
        "ANONYMIZED_TELEMETRY": "false"
      }
    }
  }
}
```

For detailed information on what data is collected and how it is handled, please refer to the [Telemetry and Data Privacy](SECURITY.md#telemetry-and-data-privacy) section in our Security Policy.

## 📝 Limitations

- Selecting specific sections of the text in a paragraph, as the MCP is relying on a11y tree. (⌛ Working on it.)
- `Type-Tool` is meant for typing text, not programming in IDE because of it types program as a whole in a file. (⌛ Working on it.)
- This MCP server can't be used to play video games 🎮.

## 🪪 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

Windows-MCP makes use of several excellent open-source projects that power its Windows automation features:

- [UIAutomation](https://github.com/yinkaisheng/Python-UIAutomation-for-Windows)

- [PyAutoGUI](https://github.com/asweigart/pyautogui)

Huge thanks to the maintainers and contributors of these libraries for their outstanding work and open-source spirit.

## 🤝Contributing

Contributions are welcome! Please see [CONTRIBUTING](CONTRIBUTING) for setup instructions and development guidelines.

Made with ❤️ by [CursorTouch](https://github.com/CursorTouch)

## Citation

```bibtex
@software{
  author       = {CursorTouch},
  title        = {Windows-MCP: Lightweight open-source project for integrating LLM agents with Windows},
  year         = {2024},
  publisher    = {GitHub},
  url={https://github.com/CursorTouch/Windows-MCP}
}
```

