# ClassNameTypePairs

Useful for adding Types to Functions & Type Functions, inspired by Vide!

> (*[exact inspiration source](<https://github.com/centau/vide/blob/f3bfc65607834370ce84a6e16722282c4d30316c/src/create.luau#:~:text=export%20type%20Instances%20=%20{>)*)

The module version shall always be whichever it was [here](<https://raw.githubusercontent.com/MaximumADHD/Roblox-Client-Tracker/master/version.txt>) at the time [this API-Dump](<https://raw.githubusercontent.com/MaximumADHD/Roblox-Client-Tracker/roblox/API-Dump.json>) was accessed and used to generate this module.

This module shall NEVER have anything functional except
- A return value `const ClassNameTypePairs = table.freeze({})`
- Type definition "***ClassNameTypePairs***" `export type ClassNameTypePairs = {`
- Return of the return value `return ClassNameTypePairs`

ONLY the contents of the "***ClassNameTypePairs***" type definition shall be ever changed.

This is required to allow for safe usage of ANY version of this module (``@*``).

To achieve **[SemVer](<https://semver.org/>)** (i.e. **[Zer0Ver](<https://0ver.org/>)** in this case), the **Major Version** part will be removed if 0, otherwise amplified:

> This is required to perform `wally publish`

e.g. `0.736.0.7361342` -> `736.0.7361342`

if **Major Version** ever becomes > 0, concat `its value * 1000` at the beginning, e.g. `1.736.0.7361342` -> `1000736.0.7361342`

> **[More info on Version here](<https://github.com/MaximumADHD/Roblox-Client-Tracker#versiontxt>)**

---

## Available Here!
- **[This repository](src/init.luau) ~ [src/init.luau](src/init.luau)**
- **[Wally](<https://wally.run/package/coffilhg/classnametypepairs>)**

    ```toml
    ClassNameTypePairs = "coffilhg/classnametypepairs@*"
    ```
- **[Rotriever](<https://github.com/Coffilhg/ClassNameTypePairs/releases/tag/v0.736.0.7361342>)**

    ```toml
    ClassNameTypePairs = "github.com/Coffilhg/Useful-Modules@0.736.0.7361342"
    ```

---

# Dependencies
- None

---

## License & Attribution

This module is licensed under the **Unlicense License**.

> See [here](LICENSE) or [here to learn more](https://unlicense.org)

Stars are appreciated!
