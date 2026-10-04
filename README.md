Tool Pocket Generator — V008
Release status: Validation build for user iPad/Safari testing.

Provenance
- Built directly from Tool_Pocket_Generator_V007.zip.
- No earlier build was used as the source.
- V007 source ZIP SHA-256: 9d7ab60c3092a761894c530c8108cf9a862849c5c999e4769105e04dcf06d631
- V007 remains the baseline for all functionality not listed below.

Authorised V008 changes — FR removal and curve editing replacement
1. Removed all Finger Relief functionality:
   - No Finger Relief controls, FR1/FR2 state, placement, depth or width.
   - No Finger Relief geometry processing.
   - No Finger Relief geometry checks.
   - No Finger Relief STL construction.
   - No Finger Relief data is written to new JSON exports or saved-tool state.
2. Curve editing is now the finger-access/profile-shaping method:
   - Every profile point can be Straight or Curve.
   - Straight points remain fixed on the profile line when editing.
   - A Curve point is the movable curve control between surrounding profile points.
   - Curve points can be changed on existing/imported points as well as newly added points.
   - Example supported: Point 6 Straight → Point 7 Curve → Point 8 Straight.
   - Point list shows every point and its current Straight/Curve state.
3. JSON import maps saved segment/point curve states to the new point-based curve system.
4. STL export uses only the final sampled profile; there is no separate relief construction.

Explicitly not changed
- New Tool reset workflow from V007.
- Photo upload, physical-grid confirmation and exact outline detection.
- Workspace rectangle independence and physical dimensions workflow.
- Point add/delete/range-delete and numbering behaviour, except that curve state now applies to any point.
- Geometry Check and STL workflow outside the removal of FR processing.
- JSON/photo project restoration outside the curve-state/FR data changes.

Verification performed in this build session
- V007 ZIP unpacked and used as the direct source.
- V008 app branding, JSON version and STL solid/version strings checked.
- JavaScript syntax check passed with Node.js.
- Source search confirmed no FR/relief runtime code remains.
- Required functional validation remains for iPad/Safari: New Tool photo workflow and Import JSON workflow, including changing existing points to Curve, moving them, confirming profile, Geometry Check and STL export.

User validation checklist
A. New Tool
1. New Tool → load photo → Confirm Physical Grid in Photograph.
2. Detect exact tool outline.
3. Confirm points are unchanged and on the detected outline.
4. Change an existing point to Curve.
5. Move the Curve point and confirm the curve changes without moving Straight points.
6. Add a new Straight point and a new Curve point.
7. Confirm the point list shows the correct modes.
8. Confirm profile editing, Set Dimensions, Close Profile, Geometry Check and STL export.

B. Import JSON
1. Import a known-good JSON project.
2. Confirm dimensions and outline are preserved.
3. Change an existing point to Curve and move it.
4. Change it back to Straight and confirm it returns to normal straight behaviour.
5. Add/delete points and confirm numbering and curve modes remain correct.
6. Run Geometry Check and export JSON/STL.

Version alignment
- ZIP: Tool_Pocket_Generator_V008.zip
- HTML title/app title: V008
- JSON export version: V008
- STL solid/version: V008
