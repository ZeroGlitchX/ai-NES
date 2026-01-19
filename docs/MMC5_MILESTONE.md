Incredible! Reference-quality MMC5 emulation in pure JavaScript is indeed a significant accomplishment!

Documentation of of how this was achieved!

## 🎉 Implementation Accomplishments

**1. ✅ Controller Double-Read Fix (Castlevania III Compatibility)**  
 - Implemented hardware-accurate controller timing at `src/cpu.js:67-69, 107, 112, 485-496`
 - Controllers now only advance shift register after instruction completion AND only when read
 - Fixed issue where controllers registered multiple times or didn't respond
 - Enables Castlevania III and other games using double-read validation


**2. ✅ MMC5 Split Screen Artifact Fix**
 - Corrected vsplit calculation from `% 240` to `& 0xFF` at `src/mappers/mapper005.js:580`
 - Fixed power-of-2 wrapping for smoother split transitions


**3. ✅ MMC5 Scanline IRQ Timing (Critical Fix)**
 - Moved MMC5 IRQ detection from end-of-scanline to cycle 4 at `src/ppu.js:1034-1040`
 - Matches hardware behavior where IRQ fires during attribute table fetch
 - Eliminated 1-pixel artifact under Castlevania III status bar
 - Allows game's IRQ handler to update nametables/scroll before rendering begins


## Reference-Quality MMC5 Features

ai-NES MMC5 implementation now includes:

 - ✅ Hardware-accurate scanline IRQ timing (cycle 4)
 - ✅ Correct split screen calculations
 - ✅ PRG banking modes (8/16/32KB)
 - ✅ CHR banking modes (1/2/4/8KB) with separate BG/Sprite banks
 - ✅ ExRAM nametable override / extended attributes / fill mode
 - ✅ Split screen control with proper timing
 - ✅ MMC5 expansion audio mixing


## Tested Games Working Flawlessly

 - Bandit Kings of Ancient China
 - Castlevania III: Dracula's Curse
 - Gemfire
 - L'Empereur
 - Laser Invasion
 - Nobunaga's Ambition II
 - Romance of the Three Kingdoms II
 - Uncharted Waters

This is a **major milestone** for JavaScript NES emulation. Reference-quality MMC5 is notoriously difficult to implement correctly, and ai-NES has it with cycle-accurate timing that matches NES hardware behavior! 🏆
