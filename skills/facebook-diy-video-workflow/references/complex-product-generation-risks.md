# Complex Product Generation Risks

Use this operational module before generating product images or video when the product has complex topology or exact functional relationships.

## High-Risk Signals

- Multiple thin cables, cords, wires, branches, loops, or crossing paths.
- Several exact endpoints, plugs, sockets, ports, hinges, clips, or attachment points.
- Many repeated small parts, such as clothes clips, hooks, teeth, rings, or fasteners.
- Dense edges, open frames, grids, lattices, transparent parts, or overlapping structures.
- A correct use method that depends on exact routing, connection order, contact points, or force direction.
- A product whose usefulness becomes false when one part count, connection, or perspective relationship changes.

## Preflight Check

1. Record the exact part count, cable path, branch topology, endpoints, connector direction, repeated-part pattern, product scale, and correct use state from the references.
2. Inspect every generated first frame at full size before creating video. Compare all critical structural facts against the source.
3. Reject the frame if it invents, removes, merges, duplicates, reconnects, bends, or relocates any critical part, or if perspective makes the product physically impossible.
4. Do not send a structurally incorrect frame into image-to-video. Motion generation usually preserves or amplifies the defect.

## Fallback Strategy

1. Use a real product photo or corrected composite as the first or last frame and request only minimal camera or environmental motion.
2. Split the video into close-up units that show one connector, cable branch, clip group, or use action at a time.
3. Use AI-generated shots for atmosphere, people, rooms, packaging, and non-critical product views; keep topology-critical shots as real footage when possible.
4. Show the verified finished-use state instead of asking the model to perform a long assembly or routing sequence in one generation.
5. Reduce simultaneous hand actions, product motion, and camera motion. Keep the product static when structural accuracy is the main task.
6. If no generated image passes the preflight check, stop the generative branch and recommend real shooting or a controlled product composite for the critical section.

## Required Feasibility Note

Before proceeding, report: risk level, topology facts that must remain exact, shots AI can safely generate, shots that require a real source, and the selected fallback.
