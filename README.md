<!---------------------- GNU General Public License 3.0 ------------------------
--                                                                            --
-- Copyright (C) 2023 Kevin Matthes                                           --
--                                                                            --
-- This program is free software: you can redistribute it and/or modify       --
-- it under the terms of the GNU General Public License as published by       --
-- the Free Software Foundation, either version 3 of the License, or          --
-- (at your option) any later version.                                        --
--                                                                            --
-- This program is distributed in the hope that it will be useful,            --
-- but WITHOUT ANY WARRANTY; without even the implied warranty of             --
-- MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the              --
-- GNU General Public License for more details.                               --
--                                                                            --
-- You should have received a copy of the GNU General Public License          --
-- along with this program.  If not, see <https://www.gnu.org/licenses/>.     --
--                                                                            --
------------------------------------------------------------------------------->

<!------------------------------------------------------------------------------
--
--  AUTHOR      Kevin Matthes
--  BRIEF       Important information regarding this project.
--  COPYRIGHT   GPL-3.0
--  DATE        2023
--  FILE        README.md
--  NOTE        See `LICENSE' for full license.
--
------------------------------------------------------------------------------->

# validate-boolean

## Summary

[![](https://bors.tech/images/badge_small.svg)](https://app.bors.tech/repositories/61987)
[![](https://github.com/kevinmatthes/validate-boolean/workflows/ci/badge.svg)](https://github.com/kevinmatthes/validate-boolean/workflows/ci)
[![](https://img.shields.io/github/license/kevinmatthes/validate-boolean)](https://github.com/kevinmatthes/validate-boolean)

A GitHub Action to check whether an input value equals either `'true'` or
`'false'`.

1. [License](#license)
2. [Description](#description)
3. [Inputs](#inputs)
   1. [`check`](#check)

## License

[![](https://img.shields.io/github/license/kevinmatthes/validate-boolean)](https://github.com/kevinmatthes/validate-boolean)

This project's license is **GPL-3.0**.  The whole license text can be found in
`LICENSE` in the main directory of this repository.  The brief version is as
follows:

> Copyright (C) 2023 Kevin Matthes
>
> This program is free software: you can redistribute it and/or modify
> it under the terms of the GNU General Public License as published by
> the Free Software Foundation, either version 3 of the License, or
> (at your option) any later version.
>
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.
>
> You should have received a copy of the GNU General Public License
> along with this program.  If not, see <https://www.gnu.org/licenses/>.

## Description

This GitHub Action will check whether the given input, `check`, equals either
the string `'true'` or the string `'false'`.  It is recommended to execute this
Action on a Linux runner.  This Action requires a Bash shell environment.

This GitHub Action has only one **mandatory** input named `check`.  This input
is of type string.  If this string is equal to `'true'` or `'false'`, this
Action will succeed.  In any other case, this Action will fail.

The branding settings were chosen due to the default use case of this Action.
The symbol `thumbs-up` shall represent the check while the colour green
symbolises the intended positive result of it ("okay").

To apply this Action, just add the following line to the step section of a
GitHub Action workflow job.

```yaml
      - uses: kevinmatthes/validate-boolean@v0.1.1
        with:
          check: ${{ inputs.value-to-check }}
```

## Inputs

### `check`

This input value is **required** and of type string.  If it equals the values
`'true'` or `'false'`, this Action will succeed.  Else, it will fail with exit
code 64.  This is the code for wrong user input according to `sysexits.h`.

<!----------------------------------------------------------------------------->
