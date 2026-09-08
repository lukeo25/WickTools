# DemBonesMrk2

Live native Wick curves, automatic animation frames, and double-click rig editing.

## Start

1. Download the updated [LukeTools.wickobj](../../LukeTools.wickobj), replace the older LukeTools object in your project, save, and reload Wick once. Activate LukeTools as usual.
2. Open **Tools → Dem Bones Mrk2** (bone-and-curve icon). The original **Dem Bones** entry is still available.
3. Select native curves on the same Wick frame and choose **Bind selected curves / Open rig** in **Build Parts**.
4. Add ordinary or stretchy bones, then pose/key them in **Animate**. Native Wick curves and their animation frames update automatically. No Commit is required.
5. Close the tool or choose **Finish editing**. Double-click the rigged artwork on the stage to reopen the saved bones and keys. **Alt + double-click** retains Wick's normal clip editing.

Extend the selected frame's exposure in Wick before making a longer animation. Mrk2 respects this exposure and does not extend frames containing unrelated artwork. Save the Wick project normally.

## What is saved

Each selected curve sits in its own synced Wick clip at its existing stacking position. The original path remains in the first internal frame. Other frames contain native curve geometry. Source shapes, bones, and keys are stored as rig data in the clip's default script, so the rig survives saving/reloading. Playback uses native frames and works with Mrk2 closed. The updated LukeTools launcher can download Mrk2 on demand when a saved rig is double-clicked.

## Scope

Live mode supports paths/compound paths, ordinary and stretchy bones, source-curve edits, and curve-point animation. Frame Bones, expression artwork, and assembled MyCharacter rigs retain the original workflow; finish live editing and disable **Edit Wick curves directly** for those features.

Do not alter the generated frames inside a managed rig clip. Transforming or copying a rig clip is not yet supported for continued bone editing; Mrk2 pauses or refuses to reconnect rather than editing another rig. Existing transformations on source paths are supported. Position artwork before binding.

Double-click reopening applies to Mrk2 rigs. Old Dem Bones commits do not include Mrk2 rig metadata. With an older LukeTools launcher, open the standalone [DemBonesMrk2.txt](DemBonesMrk2.txt) once per session; use the updated launcher for reliable reopening from saved projects.

## Validation

Automated Edge/Wick-engine checks cover native deformation, interpolated frames, original path identity, unrelated artwork, Undo, real Wick-file save/reload, double-click reopening, multiple curves, compound holes, transformed path coordinates, non-first-frame exposures, and closed-curve point animation. The launcher and configuration are integration-tested separately.

Based on [DemBones.txt](DemBones.txt), source blob 7dce618b4ae4743cba96cab31c29779ea613e7f1.
