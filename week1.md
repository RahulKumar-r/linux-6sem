# Getting Started
# Command line environment

## Terminal emulators

- GNOME Terminal - Default terminal for GNOME
- Terminal - Default terminal for macOS
- GNU Screen - Terminal multiplexer
- guake - Drop down terminal for GNOME
- konsole - Default terminal for KDE
- xfce4-terminal - Default terminal for Xfce
- xterm - Standard terminal for X11
- Termux - Terminal emulator for Android

## Command Prompt

```bash
username@hostname:~$ 
```

` ~ ` : Symbolic representation for home directory. This is working directory. Terminal opens this directory after launch. 

` @ `,  ` : `, and ` $ ` : command prompt decorators.

A command prompt can be empty.

## Simple Commands Overview

<table border=1>
  <tr>
  <th><code>Command</code></th>
  <th>Description</th>
  </tr>
  <tr id="pwd_b">
    <td><strong><code><a href="#pwd">pwd</code></strong></td>
    <td>Prints path of current/working directory.</td>
  </tr>
  <tr id="ls_b">
    <td><strong><code><a href="#ls">ls</a></code></strong></td>
    <td>Lists the files and directories.</td>
   </tr>
  <tr id="wildcards_b">
    <td><strong><code><a href="#wildcards">wildcards</code></strong></td>
    <td><code>?</code> matches single character. <code>*</code> matches 0 or more characters.</td>
   </tr>
  <tr id="cd_b">
    <td><strong><code><a href="#cd">cd</a></code></strong></td>
    <td>Change the working directory.</td>
   </tr>
  <tr id="man_b">
    <td><strong><code><a href="#man">man</a></code></strong></td>
    <td>See the mannual page for a command.</td>
   </tr>
  <tr id="uname_b">
    <td><strong><code><a href="#uname">uname</a></code></strong></td>
    <td>Print the operating system name.</td>
   </tr>
  <tr id="ps_b">
    <td><strong><code><a href="#ps">ps</a></code></strong></td>
    <td>The users currently running processes.</td>
   </tr>
  <tr id="mkdir_b">
    <td><strong><code><a href="#mkdir">mkdir</a></code></strong></td>
    <td>Create directory or directories</td>
   </tr>  
  <tr id="chmod_b">
    <td><strong><code><a href="#chmod">chmod</a></code></strong></td>
    <td>Change permissions.</td>
  </tr>
 <tr id="touch_b">
    <td><strong><code><a href="#touch">touch</a></code></strong></td>
    <td>Create a file / modify timestamp.</td>
  </tr>
  <tr id="cp_b">
    <td><strong><code><a href="#cp">cp</a></code></strong></td>
    <td>Copy file(s)</td>
  </tr>
  <tr id="mv_b">
    <td><strong><code><a href="#mv">mv</a></code></strong></td>
    <td>Move file(s) / rename a file.</td>
  </tr>
  <tr id="rm_b">
    <td><strong><code><a href="#rm">rm</a></code></strong></td>
    <td>Remove a file.</td>
  </tr>
  <tr id="alias_b">
    <td><strong><code><a href="#alias">alias</a></code></strong></td>
    <td>Create alias for a command.</td>
  </tr>
  <tr id="whoami_b">
    <td><strong><code><a href="#whoami">whoami</a></code></strong></td>
    <td>Print current user name.</td>
  </tr>
  <tr id="less_b">
    <td><strong><code><a href="#less">less</a></code></strong></td>
    <td>View files page by page.</td>
  </tr>
  <tr id="date_b">
    <td><strong><code><a href="#date">date</a></code></strong></td>
    <td>Utility for date and time</td>
  </tr>
  <tr id="ncal-and-cal_b">
    <td><strong><a href="#ncal-and-cal"><code>ncal</code> and <code>cal</code></a></strong></td>
    <td>Utility for calendar</td>
  </tr>
  <tr id="free_b">
    <td><strong><code><a href="#free">free</a></code></strong></td>
    <td>Memory statistics.</td>
  </tr>
  <tr id="groups_b">
    <td><strong><code><a href="#groups">groups</a></code></strong></td>
    <td>Groups to which user belongs.</td>
  </tr>
  <tr id="file_b">
    <td><strong><code><a href="#file">file</a></code></strong></td>
    <td>What type of file it is?</td>
  </tr>
  <tr>
    <td><strong><code>clear</code></strong></td>
    <td>Clears the screen for whole session.  Not possible to navigate the screen by scrolling.</td>
   </tr>
   <tr>
    <td><strong><code>exit</code></strong></td>
    <td>Exit shell/shell script.</td>
   </tr>
</table>

### Syntax
` root@localhost:~$ command [[options] [arguments]] `

### ` pwd `
```terminal
~$ pwd
/home/groot
```

[back](#pwd_b)
