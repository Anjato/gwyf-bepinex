# Golf With Your Friends - Cheat :)
This is a cheat menu using [BepInEx 6] (https://builds.bepinex.dev/projects/bepinex_be)


## Features
- Password bypass
- Teleport ball in hole
- Modify stroke count
- Allow jumping
- Unlimited freecam



## Notes

### Server Passwords
SessionInfo.Password = md5 hashed passwords
- Can use https://md5.j4ck.com/1 (or whatever you want) to lookup hashes


### Potential Hook Spot
BallMovement.CheckForBallHit() <-- Hooks into

 static void Postfix(BallMovement __instance, ref User ___HitCounter)
{
    if (__instance.IsBallIdle)
	{
		UnityExplorer.ExplorerCore.Log("Ball is idle!");
		__instance.HoleTimeRemaining = __instance.MaxHoleTime;
		__instance.maxHitCount = 100;
		UnityExplorer.ExplorerCore.Log($"{___HitCounter}");
	}
	else
	{
		UnityExplorer.ExplorerCore.Log("Ball is moving!");
	}
}
