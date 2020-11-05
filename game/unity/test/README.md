# Testing

## Project Modification

### Play Mode

- `IPrebuildSetup`: execute code before test starts while **running in editor**
  **on a per class basis**
- `[PrebuildSetup]`: allow several classes to share a single implementation of
  `IPrebuildSetup`
- `[assembly: TestPlayerBuildModifier(type)]` and `ITestPlayerBuildModifier`:
  execute code before test starts while **running in actual players**
  - Provides access to `BuildPlayerOptions` that is not available in
    `IPrebuildSetup`

## Resources

[Test Framework](https://docs.unity3d.com/Packages/com.unity.test-framework@1.1/manual/index.html)
[TestPlayerBuildModifier not applied in PlayMode when executed from Editor](https://forum.unity.com/threads/testplayerbuildmodifier-not-applied-in-playmode-when-executed-from-editor.864463/)
