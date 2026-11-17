# BFO Classifier

A small web tool that helps you decide where a term belongs in the **Basic Formal Ontology (BFO)**. You type an entity (for example "tank", "kicking" or "the colour of a berry"), answer a series of decision-tree questions about it, and the tool tells you which BFO class it is, with the class definition, examples and the path of answers that led there.

## What it is used for

- Classifying a term or entity in BFO as a starting point for ontology work.
- Learning how the BFO class hierarchy is structured, by walking the questions and seeing each class's definition.
- Checking commonly confused classes. The "Or maybe it's a…" cards show related classes (for example a *site* versus the *spatial region* it occupies), each with an example and a button to switch to it.
- Getting a suggested classification from Claude, which walks the same decision tree and gives a reason for each answer.

The result is a decision aid, not an authoritative ruling. Review the path and the reasons, especially for terms that can mean either a thing or what it does (for example an enzyme as a molecule versus its catalytic function).

## How it works

1. Type your entity in the top bar and press **Classify** (or press Enter).
2. Answer each question. Every option shows examples. At any question you can press **Yes, classify as …** to stop at the class you have reached.
3. The page shows the class, its **BFO class definition**, examples, notes and the class path. The breadcrumbs and Back button let you change earlier answers.
4. **Or maybe it's a…** cards list related classes with a definition, an example and a **Switch to …** button. After switching, a **Back to …** button returns you to the class you came from.
5. **Suggest with Claude** asks you to define your entity, then asks Claude to walk the tree and explain each step. You can change any step afterwards.

## Sources of the content

| Content | Source |
|---|---|
| Decision-tree questions and examples | `Updated_Decision_Tree.mmd` (Mermaid file) |
| BFO class definitions, examples, scope notes | `bfo-core.ttl` (BFO 2020 core ontology) |
| "Or maybe it's a…" relations and example text | `Laterals.xlsx` |

## Created with Claude

This tool was built through conversation with Claude, an AI assistant made by Anthropic. The decision tree, definitions and relation data come from the files listed above; Claude wrote the page code and the logic that connects them.

## Using it in Claude so "Suggest with Claude" works

The **Suggest with Claude** button only appears when the page runs as a published artifact inside claude.ai. It uses the viewer's own Claude account, so no API key is needed. If you open the HTML file directly in a browser, the manual **Classify** route still works but the Claude button stays hidden.

To set it up in your own Claude account:

1. **Download** `BFO Classifier.html`.
2. In [claude.ai](https://claude.ai), **start a new chat** and **attach** that file.
3. **Send this message:**

   > Publish this attached HTML file as an artifact exactly as it is, and declare the sample capability so its Suggest with Claude button works.

4. Claude publishes the page as an artifact in your account. **Open the artifact**.
5. Type an entity and press **Suggest with Claude**. The first time, Claude asks you to allow the page to call Claude. Allow it. Then enter a short definition of your entity (or skip it) and press **Suggest classification**.

### Notes

- **Usage:** each suggestion counts toward your own Claude usage, not the original author's.
- **Sharing:** the artifact is private to you until you choose to share it. Each person who opens a shared copy is asked for their own permission, and sharing options depend on your account or organization.
- **If the button doesn't appear:** ask Claude in the same chat to republish the page and declare the `sample` capability. If your account can't publish artifacts, only the manual Classify route is available.
- **Privacy:** the file contains no API keys or personal information. When you press Suggest with Claude, the term and any definition you type are sent to Claude, so don't enter sensitive text. The page also loads fonts from Google Fonts.
