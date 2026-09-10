# DemBonesMrk2

Live native Wick curves, automatic animation frames, and double-click rig editing.

## Start

1. Download the updated [LukeTools.wickobj](../../LukeTools.wickobj), replace the older LukeTools object in your project, save, and reload Wick once. Activate LukeTools as usual.
2. Open **Tools → Dem Bones Mrk2** (bone-and-curve icon). The original **Dem Bones** entry is still available.
3. Select native curves on the same Wick frame and choose **Bind selected curves / Open rig** in **Build Parts**.
4. Add ordinary or stretchy bones, then pose/key them in **Animate**. Native Wick curves and their animation frames update automatically. No Commit is required.
5. Close the tool or choose **Finish editing**. Double-click the rigged artwork on the stage to reopen the saved bones and keys. **Alt + double-click** retains Wick's normal clip editing.

Extend the selected frame's exposure in Wick before making a longer animation. Mrk2 respects this exposure and does not extend frames containing unrelated artwork. Save the Wick project normally.

Bone keyframe rows reappear automatically when a rig is reopened. **Create Proxy Bone Layers** places rows in the timeline containing the rig, including inside clips. The rows use the actual Wick timeline canvas, and their key diamonds remain clickable.

Bones and key overlays hide when the artwork is absent from the current frame or its layer is hidden. Deleting the associated artwork removes its temporary bone/key overlays; restoring the artwork makes them available again.

## What is saved

Each selected curve sits in its own synced Wick clip at its existing stacking position. The original path remains in the first internal frame. Other frames contain native curve geometry. Source shapes, bones, and keys are stored as rig data in the clip's default script, so the rig survives saving/reloading. Playback uses native frames and works with Mrk2 closed. The updated LukeTools launcher can download Mrk2 on demand when a saved rig is double-clicked.

## Scope

Live mode supports paths/compound paths, ordinary and stretchy bones, source-curve edits, and curve-point animation. Frame Bones, Gizmo artwork, and assembled MyCharacter rigs retain the original workflow; finish live editing and disable **Edit Wick curves directly** for those features.

You can scale, stretch, move, rotate, or flip the rigged artwork in Wick. The bones and editable curve handles follow that transform, while existing animation keys stay intact. This also works when reopening a saved rig. If several curves were bound as one rig, select and transform all of those curves together.

Do not alter the generated frames inside a managed rig clip. Copying a managed rig clip is not yet supported for continued bone editing; Mrk2 refuses to reconnect a copy to the original rig. Existing transformations on source paths are supported.

To pick up an updated tool, save your project, reload Wick, then open **Tools → Dem Bones Mrk2**. A rig paused by the earlier scaling limitation can be reopened with this version without rebuilding its bones.

Double-click reopening applies to Mrk2 rigs. Old Dem Bones commits do not include Mrk2 rig metadata. With an older LukeTools launcher, open the standalone [DemBonesMrk2.txt](DemBonesMrk2.txt) once per session; use the updated launcher for reliable reopening from saved projects.

## Validation

Automated Edge/Wick-engine checks cover native deformation, interpolated frames, original path identity, unrelated artwork, Undo, real Wick-file save/reload, double-click reopening, multiple curves, compound holes, transformed path coordinates, non-first-frame exposures, and closed-curve point animation. Transform checks include Wick Inspector scaling, non-uniform scale, rotation, mirroring, real mouse drags on bones and curve points, Wick Undo, and double-click reopening after save/reload. The launcher and configuration are integration-tested separately.

Based on [DemBones.txt](DemBones.txt), source blob 7dce618b4ae4743cba96cab31c29779ea613e7f1.

Version 2.2 additionally checks nested-timeline key setup, visible key restoration after double-click, clickable restored diamonds, empty-frame visibility, artwork deletion, and restoration.

Version 2.4 renames the user-facing Expression workspace to **Gizmo**. In **Build Parts**, **Import Selected Gizmo As Part** uses the Gizmo frame currently displayed on the Wick stage as part artwork. In **Gizmo**, **Import Selected Gizmo** imports every named internal Gizmo frame and attaches it to the selected bone immediately. No commit is required to attach or use any Bones Mrk2 bone type. Frame choices can then be keyed normally on the Wick timeline. Existing saved Expression data remains compatible; its old script controls remain internal and are no longer shown as part of the Gizmo-bone workflow.
