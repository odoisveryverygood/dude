# dude

**See what's inside. Shape what's next.**

dude is a conversational 3D workspace for exploring physical objects, editing their parts, and checking proposed changes. Ask a question, select a component, or describe a modification: dude connects the conversation to the assembly on screen.

## Explore, modify, verify

- **Explore:** open the desktop computer, mechanical keyboard, sourced Corne keyboard study, or an imported GLB assembly. Select, isolate, hide, explode, orbit, and inspect individual parts.
- **Studio:** generate a conceptual object with Gemini, edit components, ask contextual questions, and animate supported mechanisms. The mechanical dude companion follows the object and points at relevant details.
- **Review:** render the actual geometry, ask Gemini to inspect it, and evaluate supported dimensional or motion requirements. Corrections retain before/after evidence; required deterministic checks govern acceptance.
- **Circuits:** derive recognized electronic components from the Studio object, inspect their catalog pins, edit connections, and switch between 3D, illustration, and schematic views. Unknown pin mappings remain explicitly unresolved.
- **Build and export:** follow the assembly and wiring guide; inspect or download Arduino firmware, project JSON, a bill of materials, and assembly instructions. Studio and linked Circuits edits share saved project history.

## Run locally

Use Node.js 24 or newer.

```bash
git clone https://github.com/odoisveryverygood/dude.git
cd dude
npm ci
cp .env.example .env.local
# Add your server-side Gemini credentials to .env.local.
npm run dev
```

Open [localhost:3001](http://127.0.0.1:3001). See [Gemini setup](docs/GEMINI_SETUP.md) for supported endpoints and configuration. Credentials stay on the server; never use a `NEXT_PUBLIC_` variable for a provider key.

```bash
npm test
npm run typecheck
npm run build
npm start
```

Live provider tests are opt-in and require credentials. The standard test suite does not establish live provider availability or physical hardware operation.

## Try the workflows

Open `/?example=keyboard` for the keyboard mechanism, `/?example=corne` for the sourced enclosure study, or `/?example=motion-fan` for the adjustable fan motion study. Select a part and ask how it works. Describe a change, inspect the proposal and its checks, and use undo to compare with the original.

The **Parts library** adds supported sourced components with their provenance. **Sources** and **Review** live inside Studio. **Circuits** opens the linked electronic view; standalone examples are available through its New design action.

## Documentation

- [dude identity and interaction](docs/MORF.md)
- [Linked circuits, schematics, and shared history](docs/CIRCUITS.md)
- [Parts catalog and source limits](docs/CATALOG.md)
- [Measured edits](docs/MEASURED_EDITS.md) and [visual review](docs/QUALITY.md)
- [Team integration and verification limits](docs/TEAM_INTEGRATION.md)
- [Deployment configuration](docs/DEPLOYMENT.md)
- [Third-party code, models, and licenses](THIRD_PARTY.md)

## Contributing

Create a feature branch from `main` and open a pull request. Team assignments: [generation reliability](docs/team/README_TEAMMATE_1.md), [motion verification](docs/team/README_TEAMMATE_2.md), and [independent evidence](docs/team/README_TEAMMATE_3.md).

dude reuses attributed code and assets from Anatomy, Etch, and the component sources listed in [THIRD_PARTY.md](THIRD_PARTY.md). Their original licenses and notices are included.
