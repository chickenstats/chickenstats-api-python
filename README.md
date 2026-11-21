# chickenstats-api

 NHL play-by-play, stats, lines and team data, from the same pipeline behind [chickenstats.com](https://chickenstats.com).  ## Quickstart  Get a token on [your account's API page](https://chickenstats.com/account/api). The [chickenstats](https://docs.chickenstats.com) library pages for you and returns a Polars frame (or pandas), from 1.9.2 on:  ```python from chickenstats.api import ChickenStats  cs = ChickenStats(token=\"<token>\")  # or set CHICKENSTATS_API_TOKEN stats = cs.download_season_stats(season=20162017, sessions=\"P\") ```  Or, from 1.9.3, run `chickenstats login` once and call `ChickenStats()` with no token.  Anything else sends the token as a bearer token and pages with `limit` and `offset`:  ```bash curl -H \"Authorization: Bearer $TOKEN\" \\   \"https://api.chickenstats.com/api/v1/chicken_nhl/play_by_play?season=20162017&sessions=P&limit=100\" ```  A script that signs itself in uses OAuth 2.0 at `/api/v1/auth/token` (password, refresh and device grants). Log in on the website and every Try it out here uses your session.  Try it out asks for 100 rows, so the page stays quick. Leave `limit` out of your own calls and you get 10,000, or your tier's maximum if that's smaller.  ## Quotas and errors  Metered responses carry `X-Quota-Limit`, `X-Quota-Used` and `X-Quota-Remaining`, so you can watch your monthly allowance before it runs out.  | Status | What it means | | ------ | ------------- | | 400 | `limit` is over your tier's maximum rows per request | | 401 | The token is missing, invalid or expired | | 403 | Your tier doesn't include this data | | 422 | A parameter failed validation | | 429 | You're over your monthly quota, or the rate limit |  Every error comes back as `{\"detail\": ..., \"request_id\": ...}`, and the id is in the `X-Request-ID` header too. Send it along if you report a problem. 

- API version: 0.2.1
- Package version: 0.2.1

## Requirements

Python 3.9+

## Installation

```sh
pip install chickenstats-api
```

```python
import chickenstats_api
```

## Getting Started

```python

import chickenstats_api
from chickenstats_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.chickenstats.com
# See configuration.py for a list of all supported configuration parameters.
configuration = chickenstats_api.Configuration(
    host = "https://api.chickenstats.com"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

configuration.access_token = os.environ["ACCESS_TOKEN"]


# Enter a context with an instance of the API client
with chickenstats_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = chickenstats_api.AuthApi(api_client)
    device_approval = chickenstats_api.DeviceApproval() # DeviceApproval | 

    try:
        # Approve a device sign-in
        api_response = api_instance.approve_device_sign_in(device_approval)
        print("The response of AuthApi->approve_device_sign_in:\n")
        pprint(api_response)
    except ApiException as e:
        print("Exception when calling AuthApi->approve_device_sign_in: %s\n" % e)

```

## Documentation for API Endpoints

All URIs are relative to *https://api.chickenstats.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AuthApi* | [**approve_device_sign_in**](docs/AuthApi.md#approve_device_sign_in) | **POST** /api/v1/auth/device/approve | Approve a device sign-in
*AuthApi* | [**confirm_recovery**](docs/AuthApi.md#confirm_recovery) | **POST** /api/v1/auth/recovery/confirm | Confirm a recovery sign-in
*AuthApi* | [**end_all_sessions**](docs/AuthApi.md#end_all_sessions) | **DELETE** /api/v1/auth/sessions | Sign out everywhere
*AuthApi* | [**get_token**](docs/AuthApi.md#get_token) | **POST** /api/v1/auth/token | Get a token
*AuthApi* | [**make_recovery_codes**](docs/AuthApi.md#make_recovery_codes) | **POST** /api/v1/users/me/recovery-codes | Make recovery codes
*AuthApi* | [**recover_password**](docs/AuthApi.md#recover_password) | **POST** /api/v1/password-recovery/ | Send a password reset email
*AuthApi* | [**reset_password**](docs/AuthApi.md#reset_password) | **POST** /api/v1/reset-password/ | Reset a password
*AuthApi* | [**revoke_token**](docs/AuthApi.md#revoke_token) | **POST** /api/v1/auth/revoke | Sign out one session
*AuthApi* | [**set_password**](docs/AuthApi.md#set_password) | **POST** /api/v1/set-password/ | Choose a first password
*AuthApi* | [**start_device_sign_in**](docs/AuthApi.md#start_device_sign_in) | **POST** /api/v1/auth/device | Start a device sign-in
*AuthApi* | [**use_recovery_code**](docs/AuthApi.md#use_recovery_code) | **POST** /api/v1/auth/recovery | Sign in with a recovery code
*AuthApi* | [**verify_email**](docs/AuthApi.md#verify_email) | **POST** /api/v1/verify-email | Verify an email address
*AuthApi* | [**whoami**](docs/AuthApi.md#whoami) | **GET** /api/v1/auth/whoami | Who a token signs in as
*ChangesApi* | [**read_changes**](docs/ChangesApi.md#read_changes) | **GET** /api/v1/chicken_nhl/changes | Changes
*ChangesApi* | [**read_changes_game_ids**](docs/ChangesApi.md#read_changes_game_ids) | **GET** /api/v1/chicken_nhl/changes/game_ids | Game IDs with changes
*GamesApi* | [**read_game**](docs/GamesApi.md#read_game) | **GET** /api/v1/chicken_nhl/games/{game_id} | One game
*GamesApi* | [**read_games**](docs/GamesApi.md#read_games) | **GET** /api/v1/chicken_nhl/games | Games
*InferenceApi* | [**read_pred_goal**](docs/InferenceApi.md#read_pred_goal) | **GET** /api/v1/inference/pred_goal | Expected goals (pred_goal)
*LinesApi* | [**read_game_lines**](docs/LinesApi.md#read_game_lines) | **GET** /api/v1/chicken_nhl/lines/game | Line stats by game
*LinesApi* | [**read_lines_game_ids**](docs/LinesApi.md#read_lines_game_ids) | **GET** /api/v1/chicken_nhl/lines/game_ids | Game IDs with line stats
*LinesApi* | [**read_season_lines**](docs/LinesApi.md#read_season_lines) | **GET** /api/v1/chicken_nhl/lines/season | Line stats by season
*LiveApi* | [**read_live_games**](docs/LiveApi.md#read_live_games) | **GET** /api/v1/live/games | Live games
*LiveApi* | [**read_live_pbp**](docs/LiveApi.md#read_live_pbp) | **GET** /api/v1/live/play_by_play | Live play-by-play
*PlayByPlayApi* | [**read_pbp**](docs/PlayByPlayApi.md#read_pbp) | **GET** /api/v1/chicken_nhl/play_by_play | Play-by-play
*PlayByPlayApi* | [**read_pbp_game_ids**](docs/PlayByPlayApi.md#read_pbp_game_ids) | **GET** /api/v1/chicken_nhl/play_by_play/game_ids | Game IDs with play-by-play
*PlayByPlayApi* | [**read_pbp_play_ids**](docs/PlayByPlayApi.md#read_pbp_play_ids) | **GET** /api/v1/chicken_nhl/play_by_play/play_ids | Play IDs
*PlayersApi* | [**read_player**](docs/PlayersApi.md#read_player) | **GET** /api/v1/chicken_nhl/players/{api_id} | One player
*PlayersApi* | [**read_players**](docs/PlayersApi.md#read_players) | **GET** /api/v1/chicken_nhl/players | Players
*RapmApi* | [**read_rapm**](docs/RapmApi.md#read_rapm) | **GET** /api/v1/chicken_nhl/rapm | RAPM scores
*RostersApi* | [**read_roster_game_ids**](docs/RostersApi.md#read_roster_game_ids) | **GET** /api/v1/chicken_nhl/rosters/game_ids | Game IDs with rosters
*RostersApi* | [**read_rosters**](docs/RostersApi.md#read_rosters) | **GET** /api/v1/chicken_nhl/rosters | Rosters
*ShiftsApi* | [**read_shifts**](docs/ShiftsApi.md#read_shifts) | **GET** /api/v1/chicken_nhl/shifts | Shifts
*ShiftsApi* | [**read_shifts_game_ids**](docs/ShiftsApi.md#read_shifts_game_ids) | **GET** /api/v1/chicken_nhl/shifts/game_ids | Game IDs with shifts
*StandingsApi* | [**read_standings**](docs/StandingsApi.md#read_standings) | **GET** /api/v1/chicken_nhl/standings | Standings
*StatsApi* | [**read_game_stats**](docs/StatsApi.md#read_game_stats) | **GET** /api/v1/chicken_nhl/stats/game | Skater stats by game
*StatsApi* | [**read_season_stats**](docs/StatsApi.md#read_season_stats) | **GET** /api/v1/chicken_nhl/stats/season | Skater stats by season
*StatsApi* | [**read_stats_game_ids**](docs/StatsApi.md#read_stats_game_ids) | **GET** /api/v1/chicken_nhl/stats/game_ids | Game IDs with skater stats
*TeamStatsApi* | [**read_game_team_stats**](docs/TeamStatsApi.md#read_game_team_stats) | **GET** /api/v1/chicken_nhl/team_stats/game | Team stats by game
*TeamStatsApi* | [**read_season_team_stats**](docs/TeamStatsApi.md#read_season_team_stats) | **GET** /api/v1/chicken_nhl/team_stats/season | Team stats by season
*TeamStatsApi* | [**read_team_stats_game_ids**](docs/TeamStatsApi.md#read_team_stats_game_ids) | **GET** /api/v1/chicken_nhl/team_stats/game_ids | Game IDs with team stats
*TeamsApi* | [**read_teams**](docs/TeamsApi.md#read_teams) | **GET** /api/v1/chicken_nhl/teams | Teams
*UsersApi* | [**authenticator_changed**](docs/UsersApi.md#authenticator_changed) | **POST** /api/v1/users/me/authenticator/changed | Record an authenticator change
*UsersApi* | [**confirm_email_change**](docs/UsersApi.md#confirm_email_change) | **POST** /api/v1/users/email/confirm | Confirm an email change
*UsersApi* | [**create_api_token**](docs/UsersApi.md#create_api_token) | **POST** /api/v1/users/me/tokens | Make an API token
*UsersApi* | [**delete_sign_in_method**](docs/UsersApi.md#delete_sign_in_method) | **DELETE** /api/v1/users/me/sign-in-methods/{provider} | Remove a sign-in method
*UsersApi* | [**delete_user_me**](docs/UsersApi.md#delete_user_me) | **DELETE** /api/v1/users/me | Delete your account
*UsersApi* | [**list_api_tokens**](docs/UsersApi.md#list_api_tokens) | **GET** /api/v1/users/me/tokens | Your API tokens
*UsersApi* | [**read_link_token**](docs/UsersApi.md#read_link_token) | **POST** /api/v1/users/me/sign-in-methods/link-token | Start linking a sign-in method
*UsersApi* | [**read_newsletter**](docs/UsersApi.md#read_newsletter) | **GET** /api/v1/users/me/newsletter | Newsletter preference
*UsersApi* | [**read_sign_in_methods**](docs/UsersApi.md#read_sign_in_methods) | **GET** /api/v1/users/me/sign-in-methods | Your sign-in methods
*UsersApi* | [**read_usage**](docs/UsersApi.md#read_usage) | **GET** /api/v1/users/me/usage | Your usage this month
*UsersApi* | [**read_user_me**](docs/UsersApi.md#read_user_me) | **GET** /api/v1/users/me | Your account
*UsersApi* | [**request_email_change**](docs/UsersApi.md#request_email_change) | **POST** /api/v1/users/me/email | Change your email
*UsersApi* | [**resend_verification**](docs/UsersApi.md#resend_verification) | **POST** /api/v1/users/me/resend-verification | Resend the verification email
*UsersApi* | [**revoke_all_api_tokens**](docs/UsersApi.md#revoke_all_api_tokens) | **DELETE** /api/v1/users/me/tokens | Revoke every API token
*UsersApi* | [**revoke_api_token**](docs/UsersApi.md#revoke_api_token) | **DELETE** /api/v1/users/me/tokens/{token_id} | Revoke an API token
*UsersApi* | [**signup**](docs/UsersApi.md#signup) | **POST** /api/v1/users/signup | Sign up
*UsersApi* | [**update_newsletter**](docs/UsersApi.md#update_newsletter) | **PATCH** /api/v1/users/me/newsletter | Change newsletter preference
*UsersApi* | [**update_password_me**](docs/UsersApi.md#update_password_me) | **PATCH** /api/v1/users/me/password | Change your password
*UsersApi* | [**update_user_me**](docs/UsersApi.md#update_user_me) | **PATCH** /api/v1/users/me | Update your account


## Documentation For Models

 - [ApiTokenCreate](docs/ApiTokenCreate.md)
 - [ApiTokenCreated](docs/ApiTokenCreated.md)
 - [ApiTokenPublic](docs/ApiTokenPublic.md)
 - [ChangesPublic](docs/ChangesPublic.md)
 - [ChangesResponse](docs/ChangesResponse.md)
 - [DeviceApproval](docs/DeviceApproval.md)
 - [DeviceAuthorization](docs/DeviceAuthorization.md)
 - [EmailChangeConfirm](docs/EmailChangeConfirm.md)
 - [EmailChangeRequest](docs/EmailChangeRequest.md)
 - [EmailVerification](docs/EmailVerification.md)
 - [EmailVerified](docs/EmailVerified.md)
 - [GamePublic](docs/GamePublic.md)
 - [GameResponse](docs/GameResponse.md)
 - [HTTPValidationError](docs/HTTPValidationError.md)
 - [LinesGame](docs/LinesGame.md)
 - [LinesGameResponse](docs/LinesGameResponse.md)
 - [LinesSeason](docs/LinesSeason.md)
 - [LinesSeasonResponse](docs/LinesSeasonResponse.md)
 - [LinkToken](docs/LinkToken.md)
 - [LiveGamesPublic](docs/LiveGamesPublic.md)
 - [LivePbpPublic](docs/LivePbpPublic.md)
 - [LivePbpResponse](docs/LivePbpResponse.md)
 - [Message](docs/Message.md)
 - [NewPassword](docs/NewPassword.md)
 - [NewsletterPreference](docs/NewsletterPreference.md)
 - [Newsletters](docs/Newsletters.md)
 - [OAuthError](docs/OAuthError.md)
 - [PasswordRecovery](docs/PasswordRecovery.md)
 - [PbpPublic](docs/PbpPublic.md)
 - [PbpResponse](docs/PbpResponse.md)
 - [PlayerPublic](docs/PlayerPublic.md)
 - [PlayerResponse](docs/PlayerResponse.md)
 - [PredGoalResponse](docs/PredGoalResponse.md)
 - [PredGoalRow](docs/PredGoalRow.md)
 - [RapmResponse](docs/RapmResponse.md)
 - [RapmScores](docs/RapmScores.md)
 - [RecoveryCodes](docs/RecoveryCodes.md)
 - [RecoveryConfirm](docs/RecoveryConfirm.md)
 - [RecoveryRequest](docs/RecoveryRequest.md)
 - [RosterPublic](docs/RosterPublic.md)
 - [RosterResponse](docs/RosterResponse.md)
 - [ShiftsPublic](docs/ShiftsPublic.md)
 - [ShiftsResponse](docs/ShiftsResponse.md)
 - [SignInMethods](docs/SignInMethods.md)
 - [StandingsPublic](docs/StandingsPublic.md)
 - [StandingsResponse](docs/StandingsResponse.md)
 - [StatsGame](docs/StatsGame.md)
 - [StatsGameResponse](docs/StatsGameResponse.md)
 - [StatsSeason](docs/StatsSeason.md)
 - [StatsSeasonResponse](docs/StatsSeasonResponse.md)
 - [TeamPublic](docs/TeamPublic.md)
 - [TeamResponse](docs/TeamResponse.md)
 - [TeamStatsGame](docs/TeamStatsGame.md)
 - [TeamStatsGameResponse](docs/TeamStatsGameResponse.md)
 - [TeamStatsSeason](docs/TeamStatsSeason.md)
 - [TeamStatsSeasonResponse](docs/TeamStatsSeasonResponse.md)
 - [Token](docs/Token.md)
 - [UpdatePassword](docs/UpdatePassword.md)
 - [Usage](docs/Usage.md)
 - [UserPublic](docs/UserPublic.md)
 - [UserRegister](docs/UserRegister.md)
 - [UserUpdateMe](docs/UserUpdateMe.md)
 - [ValidationError](docs/ValidationError.md)
 - [ValidationErrorLocInner](docs/ValidationErrorLocInner.md)
 - [WhoAmI](docs/WhoAmI.md)


<a id="documentation-for-authorization"></a>
## Documentation For Authorization


Authentication schemes defined for the API:
<a id="OAuth2PasswordBearer"></a>
### OAuth2PasswordBearer

- **Type**: OAuth
- **Flow**: password
- **Authorization URL**: 
- **Scopes**: N/A


## Author

chicken@chickenandstats.com


