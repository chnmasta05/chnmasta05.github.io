<h1>The Ultimate UwUifier!</h1>
<div class="rendered-form">
    <div class="formbuilder-text form-group field-in-str">
        <label style="vertical-align:top" for="in-str" class="formbuilder-text-label">Input Text<span class="tooltip-element" tooltip="The text wished to be UwUified"></span></label>
        <textarea type="text" placeholder="Hello, World!" class="form-control" name="in-str" access="false" id="in-str" title="The text wished to be UwUified"></textarea>
    </div>
    <div class="formbuilder-checkbox-group form-group field-yu-smiley">
        <label for="yu-smiley" class="formbuilder-checkbox-group-label">Options<span class="tooltip-element" tooltip="Extra Options... Experiment with these!">?</span></label>
        <div class="checkbox-group">
            <div class="formbuilder-checkbox">
                <input name="yu-smiley[]" access="false" id="yu-smiley-0" value="yu" type="checkbox">
                <label for="yu-smiley-0">YUify</label>
            </div>
            <div class="formbuilder-checkbox">
                <input name="yu-smiley[]" access="false" id="yu-smiley-1" value="smiley" type="checkbox">
                <label for="yu-smiley-1">Add a Smiley uwu?</label>
            </div>
        </div>
    </div>
    <div class="formbuilder-button form-group field-uwuify">
        <button type="button" name="uwuify" value="true" access="false" style="default" id="uwuify" onclick="uwuwuwu()">UwUify!</button>
    </div>
</div>
<hr></hr>
Tip: ctrl+A to select all

<script type="text/javascript">
const SMILEYS = [
    "(ᵘʷᵘ)",
    "(ᵘﻌᵘ)",
    "(◡ ω ◡)",
    "(◡ ꒳ ◡)",
    "(◡ w ◡)",
    "(◡ ሠ ◡)",
    "(˘ω˘)",
    "(⑅˘꒳˘)",
    "(˘ᵕ˘)",
    "(˘ሠ˘)",
    "(˘³˘)",
    "(˘ε˘)",
    "(˘˘˘)",
    "( ᴜ ω ᴜ )",
    "(„ᵕᴗᵕ„)",
    "(ㅅꈍ ˘ ꈍ)",
    "(⑅˘꒳˘)",
    "( ｡ᵘ ᵕ ᵘ ｡)",
    "( ᵘ ꒳ ᵘ ✼)",
    "( ˘ᴗ˘ )",
    "(ᵕᴗ ᵕ⁎)",
    "*:･ﾟ✧(ꈍᴗꈍ)✧･ﾟ:*",
    "*˚*(ꈍ ω ꈍ).₊̣̇.",
    "(。U ω U。)",
    "(U ᵕ U❁)",
    "(U ﹏ U)",
    "(◦ᵕ ˘ ᵕ◦)",
    "ღ(U꒳Uღ)",
    "♥(。U ω U。)",
    "– ̗̀ (ᵕ꒳ᵕ) ̖́-",
    "( ͡U ω ͡U )",
    "( ͡o ᵕ ͡o )",
    "( ͡o ꒳ ͡o )",
    "( ˊ.ᴗˋ )",
    "(ᴜ‿ᴜ✿)",
    "~(˘▾˘~)",
    "(｡ᴜ‿‿ᴜ｡)",
    "uwu",
    "owo",
]

function choose(choices) {
  var index = Math.floor(Math.random() * choices.length);
  return choices[index];
}

const ER_REPLACE = /(\b\w{2,})er\b/g
const YU_REPLACE = /(?<!\b)(u|U)/g
const UWU = {"r": "w", "l": "w", "R": "W", "L": "W"}
const YU = {"u": "yu", "U": "yU"}

function do_uwu(entry) {
    entry = entry.replaceAll(ER_REPLACE, "$1a")
    for (let ch in UWU) {
        entry = entry.replaceAll(ch, UWU[ch])
    }
    return entry
}

function do_yu(entry) {
    entry = entry.replaceAll(YU_REPLACE, "y$1")
    return entry
}

function do_smiley(entry) {
    final = []
    entry = entry.split(" ")
    for (let word of entry) {
        if    (word.endsWith(".")
            || word.endsWith("?")
            || word.endsWith("!")) {
            final.push(word + " " + choose(SMILEYS))
        } else {
            final.push(word)
        }
    }
    return final.join(" ")
}

function uwu(entry, yu=false, smiley=false) {
    if (entry.length == 0)
        return entry
    if (yu)
        entry = do_yu(entry)
    entry = do_uwu(entry)
    if (smiley)
        entry = do_smiley(entry)
    return entry
}
function uwuwuwu() {
    input_str = document.getElementById("in-str").value
    flg_yu = document.getElementById("yu-smiley-0").checked
    flg_smiley = document.getElementById("yu-smiley-1").checked
    document.getElementById("in-str").value = uwu(input_str, flg_yu, flg_smiley)
}
</script>
