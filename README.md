# cjbt-nextjs-typescript-snippets

---

This extension contains code snippets for NextJS with Typescript. It is a fork of https://github.com/swyxio/swyx-react-typescript-snippets which is another fork of https://github.com/infeng/vscode-react-typescript made by cjbt.

It contains no class component APIs, assumes you use synthetic default imports, and has hooks.

Additionally it prefers function declarations over arrow function expressions and moves away from React.FC for prop scaffolding

It does a bit more based on the principle that it is easier to delete than to type, and so that we have just 3 easy to remember snippets: `rfc`, `rafc`, `rhc`.

## Installation

In order to install an extension you need to launch the Command Pallete (Ctrl + Shift + P or Cmd + Shift + P) and type Extensions.
There you have either the option to show the already installed snippets or install new ones.

Launch VS Code Quick Open (Ctrl + P or Cmd + P), paste the following command, and press enter.

`ext install cjbt-nextjs-typescript-snippets`

Alternatively you can open the extensions panel and search for 'cjbt-nextjs-typescript-snippets'.

## Supported languages (file extensions)

- TypeScript (.ts)
- TypeScript React (.tsx)

## Snippets

Below is a list of all available snippets and the triggers of each one. The **⇥** means the `TAB` key.

| Trigger | Content                                              |
| ------: | ---------------------------------------------------- |
|  `rfc→` | `create a react function component (no hooks)`       |
| `rafc→` | `create a react async function component (no hooks)` |
|  `rhc→` | `create a react hooks component`                     |

```json
{
  "React Function Component": {
    "prefix": "rfc",
    "body": [
      "type $1Props = { $2: $3 }",
      "export default function $1({ $2 }: $1Props) {",
      "    return (",
      "        $0",
      "    )",
      "};"
    ],
    "description": "Create a React Function Component"
  },
  "React Async Function Component": {
    "prefix": "rafc",
    "body": [
      "type $1Props = { $2: $3 }",
      "export default async function $1({ $2 }: $1Props) {",
      "    return (",
      "        $0",
      "    )",
      "};"
    ],
    "description": "Create a React Async Function Component"
  },
  "React Hooks Component": {
    "prefix": "rhc",
    "body": [
      "type $1Props = { $2: $3 }",
      "export default function $1({ $2 }: $1Props) {",
      "    const [${4}, set${4/(.*)/${4:/capitalize}/}] = React.useState($5);",
      "    React.useEffect(() => {}, [])",
      "    return (",
      "        ${0}",
      "    )",
      "};",
      ""
    ],
    "description": "Create a React Hooks Component."
  }
}
```

## Publishing

`vsce package`

## License

MIT
