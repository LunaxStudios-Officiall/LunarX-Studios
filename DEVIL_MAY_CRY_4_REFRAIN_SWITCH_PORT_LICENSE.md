# Licensing

# Devil May Cry 4 Refrain — Nintendo Switch Port

This is a **component-based / multi-license repository**. There is no single
license that applies to every file.

The licenses listed below grant rights only to the code and materials to which
they legally apply. They do **not** grant rights to Devil May Cry, Devil May
Cry 4 Refrain, Capcom characters, game code, game assets, logos, trademarks,
or any other proprietary game content.

## 1. touchHLE-based runtime source

The touchHLE source base and files derived from touchHLE remain licensed under
the **Mozilla Public License 2.0 (`MPL-2.0`)**.

This includes modifications made to existing touchHLE MPL-covered source files.
Existing upstream copyright, license, and attribution notices must be
preserved.

The recommended license for **new port-specific source files written from
scratch by the port contributors inside the touchHLE-based runtime** is also
`MPL-2.0`, unless a file explicitly states another valid license.

Do not apply a new LunarX copyright notice to an upstream file as though
LunarX Studios were its original author. An accurate modification notice may
be added while preserving all upstream notices.

## 2. touchHLE-based NRO executable

The touchHLE project expressly distributes its binaries under
**GNU GPL v3 or later (`GPL-3.0-or-later`)**.

Accordingly, distribution of the touchHLE-based NRO must comply with the
applicable GPL obligations, including making the complete corresponding source
for the distributed build available by the means required by the license.

The GPL status of the executable does not erase the source-level MPL-2.0
licensing or the separate licenses of included dependencies.

## 3. Forwarder NSP source

The forwarder contains several separately licensed parts:

### Sphaira / nx-hbloader loader

- `forwarder-nsp/source/main.c` — modified Sphaira hbl / nx-hbloader source:
  **ISC**
- `forwarder-nsp/source/trampoline.s` — upstream Sphaira hbl / nx-hbloader:
  **ISC**
- `forwarder-nsp/hbl.json` — derived from the Sphaira hbl configuration:
  **ISC**

The nx-hbloader copyright and ISC permission notice must be preserved.

### Sphaira-derived packer reference and packer

The pinned Sphaira repository is published under GPL v3 and no explicit
"or any later version" grant was found for the pinned code. Therefore the
conservative and legally correct designation for Sphaira-derived code is:

**`GPL-3.0-only`**

This applies to the exact Sphaira source copies in:

- `forwarder-nsp/upstream/nro.cpp`
- `forwarder-nsp/upstream/owo.cpp`
- `forwarder-nsp/upstream/nca.hpp`

and to `forwarder-nsp/build_nsp.py`, which expressly states that format
routines were adapted from Sphaira `owo.cpp`.

The current `GPL-3.0-or-later` label on `build_nsp.py` and the packer-license
fields in `PROVENANCE.json`, `release.json`, and `BUILD_README.md` should be
changed to `GPL-3.0-only` unless the Sphaira copyright holders provide a
separate later-version permission.

### Original forwarder utilities

Files that are independently original to the port and contain no Sphaira code
may be licensed by their actual copyright holder under `MPL-2.0` for
repository consistency.

The supplied source currently marks these Python utilities as
`GPL-3.0-or-later`:

- `forwarder-nsp/verify_nsp.py`
- `forwarder-nsp/test_package.py`
- `forwarder-nsp/test_hidden_entry.py`

If those files are wholly original and the current copyright holder intended
that grant, it may remain. They must not be treated as evidence that
Sphaira-derived code also has an "or later" grant.

## 4. Dynarmic and its externals

Dynarmic itself remains under **0BSD**.

The included Switch patch is mixed-license because it changes both Dynarmic
and Oaknut source:

- Dynarmic `address_space.*` changes: **0BSD**
- Oaknut `code_block.hpp` changes: **MIT**

For clarity, future public releases should split the mixed patch into separate
component-specific patch files or document the path-level license mapping
adjacent to the patch.

Dynarmic's bundled externals retain their own licenses, including MIT,
BSD-3-Clause, Boost-1.0, and other terms listed in
`THIRD_PARTY_NOTICES.md`.

## 5. SDL2

SDL2 remains under the **Zlib** license.

The Switch SDL patch is a derivative modification of SDL2 and remains subject
to SDL2's applicable license/notices. SDL's Zlib terms require altered source
versions to be plainly marked and the notice not to be removed.

Nested third-party material inside the SDL source tree retains its own license.
For example, HIDAPI is offered under its upstream alternative license choices,
and the bundled bitmap-font demo material contains its own license.

## 6. OpenAL Soft

The OpenAL Soft core source used by the port contains an explicit
**GNU Library/Lesser GPL version 2 or later** grant
(`LGPL-2.0-or-later` in modern SPDX notation).

The Switch OpenAL patch must remain under terms compatible with that upstream
code. Some OpenAL Soft utility programs have separate GPL-2.0-or-later
notices and retain those terms.

## 7. libnx / devkitPro / external toolchain components

libnx is licensed under **ISC**.

The build also links components supplied by the installed devkitPro/toolchain
and portlibs, including Mesa-related libraries, newlib, libstdc++, and GCC
runtime components. Those components retain their own licenses and exceptions.
Their exact package notices must be captured from the exact installed package
versions before the public binary release is declared compliance-complete.

## 8. Rust dependencies and local forks

Rust dependencies retain their individual licenses.

In particular:

- `vendor/switch-corosensei`: `MIT OR Apache-2.0`
- `vendor/switch-libc`: `MIT OR Apache-2.0`
- Symphonia family: `MPL-2.0`
- other Cargo dependencies: see `RUST_RUNTIME_DEPENDENCIES.csv`

Local Switch/Horizon modifications do not erase those upstream licenses.

## 9. touchHLE support dylibs and fonts

The files in `touchHLE_dylibs/` and `touchHLE_fonts/` are separately licensed.
Preserve their bundled README/COPYING/LICENSE files.

## 10. Capcom game and intellectual property

This repository does not license and must not distribute:

- `game.ipa`;
- the original game executable or extracted game files;
- Capcom artwork, character art, logos, music, video, or other game assets;
- Capcom trademarks.

Users must provide their own lawfully obtained game copy separately.

The current `runtime-nro/switch/assets/icon.jpg` is derived from a
`DMC4_Refrain_Cover_Source.png` and depicts recognizable Devil May Cry
character artwork. No redistribution permission for that artwork was supplied
with the source. It must be replaced with an original, non-infringing project
icon before public publication unless specific authorization is obtained.

## 11. Port identity and forks

Open-source licensing permits forks and modifications subject to each
component's license.

Required upstream copyright/license notices must be preserved. Modified
versions should accurately identify themselves as modified forks and should
not falsely claim to be the original LunarX Studios release.

The software licenses in this repository do not grant rights to use LunarX
Studios branding in a misleading way or to imply endorsement of a fork.

See `PORT_NOTICE.md` and `THIRD_PARTY_NOTICES.md`.
