# Pack template

A valid, empty [Quiver pack](https://github.com/agent-quiver/pack-standard). Press **Use this template**, then:

1. Edit `quiver-pack.yaml`: the `id` is `<your namespace>/<your repository>`.
2. Replace `skills/hello/` with your own artifacts. Each one is a directory with a `quiver.yaml` and its
   entrypoint (`SKILL.md` for a skill, a rules or reference file for a resource).
3. Record changes in `CHANGELOG.md` and release with a tag `vX.Y.Z` that equals `version`.
4. To list a public pack, open a pull request on
   [`agent-quiver/catalog`](https://github.com/agent-quiver/catalog).

The layout and the rules are in [`STANDARD.md`](https://github.com/agent-quiver/pack-standard/blob/main/STANDARD.md).
