# chickenstats-api

API for downloading NHL data

- API version: 0.1.9
- Package version: 0.1.9

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
    api_instance = chickenstats_api.ChangesApi(api_client)
    limit = 56 # int | Rows per page. When omitted, 10,000 or your tier's maximum, whichever is smaller; the response's `limit` says which. A value over your tier's maximum is refused with a 400. (optional)
    offset = 0 # int |  (optional) (default to 0)
    with_total = True # bool | Include the exact total row count. Set false on broad queries: the count scans every matching row, which on a season-wide filter costs far more than the page itself. `total` is then -1 and `has_next` still works. (optional) (default to True)
    season = [56] # List[int] |  (optional)
    sessions = ['sessions_example'] # List[str] |  (optional)
    game_id = [56] # List[int] |  (optional)
    event_team = ['event_team_example'] # List[str] |  (optional)
    period = [56] # List[int] |  (optional)
    include = ['include_example'] # List[str] |  (optional)

    try:
        # Read Changes
        api_response = api_instance.read_changes(limit=limit, offset=offset, with_total=with_total, season=season, sessions=sessions, game_id=game_id, event_team=event_team, period=period, include=include)
        print("The response of ChangesApi->read_changes:\n")
        pprint(api_response)
    except ApiException as e:
        print("Exception when calling ChangesApi->read_changes: %s\n" % e)

```

## Documentation for API Endpoints

All URIs are relative to *https://api.chickenstats.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ChangesApi* | [**read_changes**](docs/ChangesApi.md#read_changes) | **GET** /api/v1/chicken_nhl/changes | Read Changes
*ChangesApi* | [**read_changes_game_ids**](docs/ChangesApi.md#read_changes_game_ids) | **GET** /api/v1/chicken_nhl/changes/game_ids | Read Changes Game Ids
*GamesApi* | [**read_game**](docs/GamesApi.md#read_game) | **GET** /api/v1/chicken_nhl/games/{game_id} | Read Game
*GamesApi* | [**read_games**](docs/GamesApi.md#read_games) | **GET** /api/v1/chicken_nhl/games | Read Games
*InferenceApi* | [**read_pred_goal**](docs/InferenceApi.md#read_pred_goal) | **GET** /api/v1/inference/pred_goal | Read Pred Goal
*LinesApi* | [**read_game_lines**](docs/LinesApi.md#read_game_lines) | **GET** /api/v1/chicken_nhl/lines/game | Read Game Lines
*LinesApi* | [**read_lines_game_ids**](docs/LinesApi.md#read_lines_game_ids) | **GET** /api/v1/chicken_nhl/lines/game_ids | Read Lines Game Ids
*LinesApi* | [**read_season_lines**](docs/LinesApi.md#read_season_lines) | **GET** /api/v1/chicken_nhl/lines/season | Read Season Lines
*LiveApi* | [**read_live_games**](docs/LiveApi.md#read_live_games) | **GET** /api/v1/live/games | Read Live Games
*LiveApi* | [**read_live_pbp**](docs/LiveApi.md#read_live_pbp) | **GET** /api/v1/live/play_by_play | Read Live Pbp
*LoginApi* | [**login_firebase_token**](docs/LoginApi.md#login_firebase_token) | **POST** /api/v1/login/firebase-token | Login Firebase Token
*LoginApi* | [**login_refresh**](docs/LoginApi.md#login_refresh) | **POST** /api/v1/login/refresh | Login Refresh
*LoginApi* | [**login_verify_token**](docs/LoginApi.md#login_verify_token) | **POST** /api/v1/login/verify-token | Login Verify Token
*LoginApi* | [**recover_password**](docs/LoginApi.md#recover_password) | **POST** /api/v1/password-recovery/{email} | Recover Password
*LoginApi* | [**recover_password_html_content**](docs/LoginApi.md#recover_password_html_content) | **POST** /api/v1/password-recovery-html-content/{email} | Recover Password Html Content
*LoginApi* | [**reset_password**](docs/LoginApi.md#reset_password) | **POST** /api/v1/reset-password/ | Reset Password
*LoginApi* | [**test_token**](docs/LoginApi.md#test_token) | **POST** /api/v1/login/test-token | Test Token
*PlayByPlayApi* | [**read_pbp**](docs/PlayByPlayApi.md#read_pbp) | **GET** /api/v1/chicken_nhl/play_by_play | Read Pbp
*PlayByPlayApi* | [**read_pbp_game_ids**](docs/PlayByPlayApi.md#read_pbp_game_ids) | **GET** /api/v1/chicken_nhl/play_by_play/game_ids | Read Pbp Game Ids
*PlayByPlayApi* | [**read_pbp_play_ids**](docs/PlayByPlayApi.md#read_pbp_play_ids) | **GET** /api/v1/chicken_nhl/play_by_play/play_ids | Read Pbp Play Ids
*PlayersApi* | [**read_player**](docs/PlayersApi.md#read_player) | **GET** /api/v1/chicken_nhl/players/{api_id} | Read Player
*PlayersApi* | [**read_players**](docs/PlayersApi.md#read_players) | **GET** /api/v1/chicken_nhl/players | Read Players
*RapmApi* | [**read_rapm**](docs/RapmApi.md#read_rapm) | **GET** /api/v1/chicken_nhl/rapm | Read Rapm
*RostersApi* | [**read_roster_game_ids**](docs/RostersApi.md#read_roster_game_ids) | **GET** /api/v1/chicken_nhl/rosters/game_ids | Read Roster Game Ids
*RostersApi* | [**read_rosters**](docs/RostersApi.md#read_rosters) | **GET** /api/v1/chicken_nhl/rosters | Read Rosters
*ShiftsApi* | [**read_shifts**](docs/ShiftsApi.md#read_shifts) | **GET** /api/v1/chicken_nhl/shifts | Read Shifts
*ShiftsApi* | [**read_shifts_game_ids**](docs/ShiftsApi.md#read_shifts_game_ids) | **GET** /api/v1/chicken_nhl/shifts/game_ids | Read Shifts Game Ids
*StandingsApi* | [**read_standings**](docs/StandingsApi.md#read_standings) | **GET** /api/v1/chicken_nhl/standings | Read Standings
*StatsApi* | [**read_game_stats**](docs/StatsApi.md#read_game_stats) | **GET** /api/v1/chicken_nhl/stats/game | Read Game Stats
*StatsApi* | [**read_season_stats**](docs/StatsApi.md#read_season_stats) | **GET** /api/v1/chicken_nhl/stats/season | Read Season Stats
*StatsApi* | [**read_stats_game_ids**](docs/StatsApi.md#read_stats_game_ids) | **GET** /api/v1/chicken_nhl/stats/game_ids | Read Stats Game Ids
*TeamStatsApi* | [**read_game_team_stats**](docs/TeamStatsApi.md#read_game_team_stats) | **GET** /api/v1/chicken_nhl/team_stats/game | Read Game Team Stats
*TeamStatsApi* | [**read_season_team_stats**](docs/TeamStatsApi.md#read_season_team_stats) | **GET** /api/v1/chicken_nhl/team_stats/season | Read Season Team Stats
*TeamStatsApi* | [**read_team_stats_game_ids**](docs/TeamStatsApi.md#read_team_stats_game_ids) | **GET** /api/v1/chicken_nhl/team_stats/game_ids | Read Team Stats Game Ids
*TeamsApi* | [**read_teams**](docs/TeamsApi.md#read_teams) | **GET** /api/v1/chicken_nhl/teams | Read Teams
*UsersApi* | [**delete_user_me**](docs/UsersApi.md#delete_user_me) | **DELETE** /api/v1/users/me | Delete User Me
*UsersApi* | [**get_programmatic_credentials**](docs/UsersApi.md#get_programmatic_credentials) | **GET** /api/v1/users/me/programmatic-credentials | Get Programmatic Credentials
*UsersApi* | [**read_user_me**](docs/UsersApi.md#read_user_me) | **GET** /api/v1/users/me | Read User Me
*UsersApi* | [**resend_verification**](docs/UsersApi.md#resend_verification) | **POST** /api/v1/users/me/resend-verification | Resend Verification
*UsersApi* | [**rotate_programmatic_credentials**](docs/UsersApi.md#rotate_programmatic_credentials) | **POST** /api/v1/users/me/programmatic-credentials/rotate | Rotate Programmatic Credentials
*UsersApi* | [**signup**](docs/UsersApi.md#signup) | **POST** /api/v1/users/signup | Signup
*UsersApi* | [**update_password_me**](docs/UsersApi.md#update_password_me) | **PATCH** /api/v1/users/me/password | Update Password Me
*UsersApi* | [**update_user_me**](docs/UsersApi.md#update_user_me) | **PATCH** /api/v1/users/me | Update User Me


## Documentation For Models

 - [ChangesPublic](docs/ChangesPublic.md)
 - [ChangesResponse](docs/ChangesResponse.md)
 - [GamePublic](docs/GamePublic.md)
 - [GameResponse](docs/GameResponse.md)
 - [HTTPValidationError](docs/HTTPValidationError.md)
 - [IdToken](docs/IdToken.md)
 - [LinesCreate](docs/LinesCreate.md)
 - [LinesGame](docs/LinesGame.md)
 - [LinesGameResponse](docs/LinesGameResponse.md)
 - [LinesPublic](docs/LinesPublic.md)
 - [LinesSeason](docs/LinesSeason.md)
 - [LinesSeasonResponse](docs/LinesSeasonResponse.md)
 - [LiveGamesPublic](docs/LiveGamesPublic.md)
 - [LivePbpPublic](docs/LivePbpPublic.md)
 - [LivePbpResponse](docs/LivePbpResponse.md)
 - [Message](docs/Message.md)
 - [NewPassword](docs/NewPassword.md)
 - [PbpPublic](docs/PbpPublic.md)
 - [PbpResponse](docs/PbpResponse.md)
 - [PlayerPublic](docs/PlayerPublic.md)
 - [PlayerResponse](docs/PlayerResponse.md)
 - [PredGoalResponse](docs/PredGoalResponse.md)
 - [PredGoalRow](docs/PredGoalRow.md)
 - [ProgrammaticCredentials](docs/ProgrammaticCredentials.md)
 - [RapmResponse](docs/RapmResponse.md)
 - [RapmScores](docs/RapmScores.md)
 - [RefreshTokenRequest](docs/RefreshTokenRequest.md)
 - [RosterPublic](docs/RosterPublic.md)
 - [RosterResponse](docs/RosterResponse.md)
 - [ShiftsPublic](docs/ShiftsPublic.md)
 - [ShiftsResponse](docs/ShiftsResponse.md)
 - [StandingsPublic](docs/StandingsPublic.md)
 - [StandingsResponse](docs/StandingsResponse.md)
 - [StatsCreate](docs/StatsCreate.md)
 - [StatsGame](docs/StatsGame.md)
 - [StatsGameResponse](docs/StatsGameResponse.md)
 - [StatsSeason](docs/StatsSeason.md)
 - [StatsSeasonResponse](docs/StatsSeasonResponse.md)
 - [TeamPublic](docs/TeamPublic.md)
 - [TeamResponse](docs/TeamResponse.md)
 - [TeamStatsCreate](docs/TeamStatsCreate.md)
 - [TeamStatsGame](docs/TeamStatsGame.md)
 - [TeamStatsGameResponse](docs/TeamStatsGameResponse.md)
 - [TeamStatsPublic](docs/TeamStatsPublic.md)
 - [TeamStatsSeason](docs/TeamStatsSeason.md)
 - [TeamStatsSeasonResponse](docs/TeamStatsSeasonResponse.md)
 - [Token](docs/Token.md)
 - [UpdatePassword](docs/UpdatePassword.md)
 - [UserCreate](docs/UserCreate.md)
 - [UserPublic](docs/UserPublic.md)
 - [UserRegister](docs/UserRegister.md)
 - [UserUpdate](docs/UserUpdate.md)
 - [UserUpdateMe](docs/UserUpdateMe.md)
 - [UsersPublic](docs/UsersPublic.md)
 - [ValidationError](docs/ValidationError.md)
 - [ValidationErrorLocInner](docs/ValidationErrorLocInner.md)


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


