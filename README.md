# ![LOGO](logo.png) VocaDB **flow**ground Connector

## Description

A generated **flow**ground connector for the VocaDB API (version v1).

Generated from: https://api.apis.guru/v2/specs/vocadb.net/v1/swagger.json<br/>
Generated at: 2019-05-07T17:44:45+03:00

## API Description



## Authorization

This API does not require authorization.

## Actions

### Gets a list of recent activity entries.

> Entries are always returned sorted from newest to oldest.<br/>
>             Activity for deleted entries is not returned.

*Tags:* `ActivityEntryApi`

#### Input Parameters
* `before` - _optional_ - Filter to return activity entries only before this date. Optional, by default no filter.
* `since` - _optional_ - Filter to return activity entries only after this date. Optional, by default no filter.
* `userId` - _optional_ - Filter by user Id. Optional, by default no filter.
* `editEvent` - _optional_ - Filter by entry edit event (either Created or Updated). Optional, by default no filter.
    Possible values: Created, Updated, Deleted, Restored.
* `maxResults` - _optional_ - Maximum number of results to return. Default 50. Maximum value 500.
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `fields` - _optional_ - Optional fields.
    Possible values: None, ArchivedVersion, Entry.
* `entryFields` - _optional_ - Optional fields for entries.
    Possible values: None, AdditionalNames, Description, MainPicture, Names, PVs, Tags, WebLinks.
* `lang` - _optional_ - Content language preference.
    Possible values: Default, Japanese, Romaji, English.

### Gets a page of albums.

*Tags:* `AlbumApi`

#### Input Parameters
* `query` - _optional_ - Album name query (optional).
* `discTypes` - _optional_ - Disc type. By default nothing. Possible values are Album, Single, EP, SplitAlbum, Compilation, Video, Other. Note: only one type supported for now.
    Possible values: Unknown, Album, Single, EP, SplitAlbum, Compilation, Video, Artbook, Game, Fanmade, Instrumental, Other.
* `tagName` - _optional_ - Filter by tag name (optional). This filter can be specified multiple times.
* `tagId` - _optional_ - Filter by tag Id (optional). This filter can be specified multiple times.
* `childTags` - _optional_ - Include child tags, if the tags being filtered by have any.
* `artistId` - _optional_ - Filter by artist Id (optional).
* `artistParticipationStatus` - _optional_ - Filter by artist participation status. Only valid if artistId is specified.
            Everything (default): Show all albums by that artist (no filter).
            OnlyMainAlbums: Show only main albums by that artist.
            OnlyCollaborations: Show only collaborations by that artist.
    Possible values: Everything, OnlyMainAlbums, OnlyCollaborations.
* `childVoicebanks` - _optional_ - Include child voicebanks, if the artist being filtered by has any.
* `includeMembers` - _optional_ - Include members of groups. This applies if {artistId} is a group.
* `barcode` - _optional_ - Filter by album barcode (optional).
* `status` - _optional_ - Filter by entry status (optional).
    Possible values: Draft, Finished, Approved, Locked.
* `releaseDateAfter` - _optional_ - Filter by albums whose release date is after this date (inclusive).
* `releaseDateBefore` - _optional_ - Filter by albums whose release date is before this date (exclusive).
* `advancedFilters` - _optional_ - List of advanced filters (optional).
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 50).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - Sort rule (optional, defaults to Name). 
            Possible values are None, Name, ReleaseDate, ReleaseDateWithNulls, AdditionDate, RatingAverage, RatingTotal, NameThenReleaseDate.
    Possible values: None, Name, ReleaseDate, ReleaseDateWithNulls, AdditionDate, RatingAverage, RatingTotal, NameThenReleaseDate, CollectionCount.
* `preferAccurateMatches` - _optional_ - Whether the search should prefer accurate matches. 
            If this is true, entries that match by prefix will be moved first, instead of being sorted alphabetically.
            Requires a text query. Does not support pagination.
            This is mostly useful for autocomplete boxes.
* `deleted` - _optional_ - Whether to search for deleted entries.
            If this is true, only deleted entries will be returned.
            If this is false (default), deleted entries are not returned.
* `nameMatchMode` - _optional_ - Match mode for artist name (optional, defaults to Exact).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `fields` - _optional_ - Optional fields (optional). Possible values are artists, names, pvs, tags, tracks, webLinks.
    Possible values: None, AdditionalNames, Artists, Description, Discs, Identifiers, MainPicture, Names, PVs, ReleaseEvent, Tags, Tracks, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Deletes a comment.

> Normal users can delete their own comments, moderators can delete all comments.<br/>
>             Requires login.

*Tags:* `AlbumApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be deleted.

### Updates a comment.

> Normal users can edit their own comments, moderators can edit all comments.<br/>
>             Requires login.

*Tags:* `AlbumApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be edited.

### Gets a list of album names. Ideal for autocomplete boxes.

*Tags:* `AlbumApi`

#### Input Parameters
* `query` - _optional_ - Text query.
* `nameMatchMode` - _optional_ - Name match mode.
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `maxResults` - _optional_ - Maximum number of results.

### Gets list of upcoming or recent albums, same as front page.

> Output is cached for 1 hour.

*Tags:* `AlbumApi`

#### Input Parameters
* `languagePreference` - _optional_
    Possible values: Default, Japanese, Romaji, English.
* `fields` - _optional_
    Possible values: None, AdditionalNames, Artists, Description, Discs, Identifiers, MainPicture, Names, PVs, ReleaseEvent, Tags, Tracks, WebLinks.

### Gets list of top rated albums, same as front page.

> Output is cached for 1 hour.

*Tags:* `AlbumApi`

#### Input Parameters
* `languagePreference` - _optional_
    Possible values: Default, Japanese, Romaji, English.
* `fields` - _optional_
    Possible values: None, AdditionalNames, Artists, Description, Discs, Identifiers, MainPicture, Names, PVs, ReleaseEvent, Tags, Tracks, WebLinks.

### Deletes an album.

*Tags:* `AlbumApi`

#### Input Parameters
* `id` - _required_ - ID of the album to be deleted.
* `notes` - _optional_ - Notes.

### Gets an album by Id.

*Tags:* `AlbumApi`

#### Input Parameters
* `id` - _required_ - Album Id (required).
* `fields` - _optional_ - Optional fields (optional). Possible values are artists, names, pvs, tags, tracks, webLinks.
    Possible values: None, AdditionalNames, Artists, Description, Discs, Identifiers, MainPicture, Names, PVs, ReleaseEvent, Tags, Tracks, WebLinks.
* `songFields` - _optional_ - Optional fields for tracks, if included (optional).
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a list of comments for an album.

> Pagination and sorting might be added later.

*Tags:* `AlbumApi`

#### Input Parameters
* `id` - _required_ - ID of the album whose comments to load.

### Posts a new comment.

*Tags:* `AlbumApi`

#### Input Parameters
* `id` - _required_ - ID of the album for which to create the comment.

### AlbumApi_GetReviews

*Tags:* `AlbumApi`

#### Input Parameters
* `id` - _required_
* `languageCode` - _optional_

### AlbumApi_PostReview

*Tags:* `AlbumApi`

#### Input Parameters
* `id` - _required_

### AlbumApi_DeleteReview

*Tags:* `AlbumApi`

#### Input Parameters
* `reviewId` - _required_
* `id` - _required_

### Gets tracks for an album.

*Tags:* `AlbumApi`

#### Input Parameters
* `id` - _required_ - Album ID (required).
* `fields` - _optional_ - List of optional fields (optional). Possible values are Albums, Artists, Names, PVs, Tags, ThumbUrl, WebLinks.
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets tracks for an album formatted using the CSV format string.

*Tags:* `AlbumApi`

#### Input Parameters
* `id` - _required_ - Album ID.
* `field` - _optional_ - Field to be included, for example "featvocalists" or "url". Can be specified multiple times.
* `lang` - _optional_ - Language preference.
    Possible values: Default, Japanese, Romaji, English.

### AlbumApi_GetUserCollections

*Tags:* `AlbumApi`

#### Input Parameters
* `id` - _required_
* `languagePreference` - _optional_
    Possible values: Default, Japanese, Romaji, English.

### Find artists.

*Tags:* `ArtistApi`

#### Input Parameters
* `query` - _optional_ - Artist name query (optional).
* `artistTypes` - _optional_ - Filtered artist type (optional).
* `allowBaseVoicebanks` - _optional_ - Allow base voicebanks. If false, only root voicebanks will be allowed. Only affects voice synthesizers that can have base voicebanks.
* `tagName` - _optional_ - Filter by tag name (optional).
* `tagId` - _optional_ - Filter by tag Id (optional). This filter can be specified multiple times.
* `childTags` - _optional_ - Include child tags, if the tags being filtered by have any.
* `followedByUserId` - _optional_ - Filter by user following the artists. By default there is no filtering.
* `status` - _optional_ - Filter by entry status (optional).
    Possible values: Draft, Finished, Approved, Locked.
* `advancedFilters` - _optional_ - List of advanced filters (optional).
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 100).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - Sort rule (optional, defaults to Name). Possible values are None, Name, AdditionDate, AdditionDateAsc.
    Possible values: None, Name, AdditionDate, AdditionDateAsc, ReleaseDate, SongCount, SongRating, FollowerCount.
* `preferAccurateMatches` - _optional_ - Whether the search should prefer accurate matches. 
            If this is true, entries that match by prefix will be moved first, instead of being sorted alphabetically.
            Requires a text query. Does not support pagination.
            This is mostly useful for autocomplete boxes.
* `nameMatchMode` - _optional_ - Match mode for artist name (optional, defaults to Exact).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `fields` - _optional_ - List of optional fields (optional). Possible values are Description, Groups, Members, Names, Tags, WebLinks.
    Possible values: None, AdditionalNames, ArtistLinks, ArtistLinksReverse, BaseVoicebank, Description, MainPicture, Names, Tags, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Deletes a comment.

> Normal users can delete their own comments, moderators can delete all comments.<br/>
>             Requires login.

*Tags:* `ArtistApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be deleted.

### Updates a comment.

> Normal users can edit their own comments, moderators can edit all comments.<br/>
>             Requires login.

*Tags:* `ArtistApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be edited.

### Gets a list of artist names. Ideal for autocomplete boxes.

*Tags:* `ArtistApi`

#### Input Parameters
* `query` - _optional_ - Text query.
* `nameMatchMode` - _optional_ - Name match mode.
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `maxResults` - _optional_ - Maximum number of results.

### Deletes an artist.

*Tags:* `ArtistApi`

#### Input Parameters
* `id` - _required_ - ID of the artist to be deleted.
* `notes` - _optional_ - Notes.

### Gets an artist by Id.

*Tags:* `ArtistApi`

#### Input Parameters
* `id` - _required_ - Artist ID (required).
* `fields` - _optional_ - List of optional fields (optional). Possible values are Description, Groups, Members, Names, Tags, WebLinks.
    Possible values: None, AdditionalNames, ArtistLinks, ArtistLinksReverse, BaseVoicebank, Description, MainPicture, Names, Tags, WebLinks.
* `relations` - _optional_ - List of artist relations (optional). Possible values are LatestAlbums, PopularAlbums, LatestSongs, PopularSongs, All
    Possible values: None, LatestAlbums, LatestEvents, LatestSongs, PopularAlbums, PopularSongs, All.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a list of comments for an artist.

> Pagination and sorting might be added later.

*Tags:* `ArtistApi`

#### Input Parameters
* `id` - _required_ - ID of the artist whose comments to load.

### Posts a new comment.

*Tags:* `ArtistApi`

#### Input Parameters
* `id` - _required_ - ID of the artist for which to create the comment.

### Gets a list of comments for an entry.

*Tags:* `CommentApi`

#### Input Parameters
* `entryType` - _required_ - Entry type.
    Possible values: Undefined, Album, Artist, DiscussionTopic, PV, ReleaseEvent, ReleaseEventSeries, Song, SongList, Tag, User.
* `entryId` - _required_ - ID of the entry whose comments to load.

### Posts a new comment.

*Tags:* `CommentApi`

#### Input Parameters
* `entryType` - _required_ - Entry type.
    Possible values: Undefined, Album, Artist, DiscussionTopic, PV, ReleaseEvent, ReleaseEventSeries, Song, SongList, Tag, User.

### Deletes a comment.

> Normal users can delete their own comments, moderators can delete all comments.<br/>
>             Requires login.

*Tags:* `CommentApi`

#### Input Parameters
* `entryType` - _required_ - Entry type.
    Possible values: Undefined, Album, Artist, DiscussionTopic, PV, ReleaseEvent, ReleaseEventSeries, Song, SongList, Tag, User.
* `commentId` - _required_ - ID of the comment to be deleted.

### Updates a comment.

> Normal users can edit their own comments, moderators can edit all comments.<br/>
>             Requires login.

*Tags:* `CommentApi`

#### Input Parameters
* `entryType` - _required_ - Entry type.
    Possible values: Undefined, Album, Artist, DiscussionTopic, PV, ReleaseEvent, ReleaseEventSeries, Song, SongList, Tag, User.
* `commentId` - _required_ - ID of the comment to be edited.

### DiscussionApi_DeleteComment

*Tags:* `DiscussionApi`

#### Input Parameters
* `commentId` - _required_

### DiscussionApi_PostEditComment

*Tags:* `DiscussionApi`

#### Input Parameters
* `commentId` - _required_

### DiscussionApi_GetFolders

*Tags:* `DiscussionApi`

#### Input Parameters
* `fields` - _optional_
    Possible values: None, LastTopic, TopicCount.

### DiscussionApi_PostNewFolder

*Tags:* `DiscussionApi`

### DiscussionApi_GetTopicsForFolder

*Tags:* `DiscussionApi`

#### Input Parameters
* `folderId` - _required_
* `fields` - _optional_
    Possible values: None, Comments, CommentCount, Content, LastComment, All.

### DiscussionApi_PostNewTopic

*Tags:* `DiscussionApi`

#### Input Parameters
* `folderId` - _required_

### DiscussionApi_GetTopics

*Tags:* `DiscussionApi`

#### Input Parameters
* `folderId` - _optional_
* `start` - _optional_
* `maxResults` - _optional_
* `getTotalCount` - _optional_
* `sort` - _optional_
    Possible values: None, Name, DateCreated, LastCommentDate.
* `fields` - _optional_
    Possible values: None, Comments, CommentCount, Content, LastComment, All.

### DiscussionApi_DeleteTopic

*Tags:* `DiscussionApi`

#### Input Parameters
* `topicId` - _required_

### DiscussionApi_GetTopic

*Tags:* `DiscussionApi`

#### Input Parameters
* `topicId` - _required_
* `fields` - _optional_
    Possible values: None, Comments, CommentCount, Content, LastComment, All.

### DiscussionApi_PostEditTopic

*Tags:* `DiscussionApi`

#### Input Parameters
* `topicId` - _required_

### DiscussionApi_PostNewComment

*Tags:* `DiscussionApi`

#### Input Parameters
* `topicId` - _required_

### Find entries.

*Tags:* `EntryApi`

#### Input Parameters
* `query` - _optional_ - Entry name query (optional).
* `tagName` - _optional_ - Filter by tag name (optional).
* `tagId` - _optional_ - Filter by tag Id (optional).
* `childTags` - _optional_ - Include child tags, if the tags being filtered by have any.
* `status` - _optional_ - Filter by entry status (optional).
    Possible values: Draft, Finished, Approved, Locked.
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 30).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - Sort rule (optional, defaults to Name). Possible values are None, Name, AdditionDate.
    Possible values: None, Name, AdditionDate, ActivityDate.
* `nameMatchMode` - _optional_ - Match mode for entry name (optional, defaults to Exact).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `fields` - _optional_ - List of optional fields (optional). Possible values are Description, MainPicture, Names, Tags, WebLinks.
    Possible values: None, AdditionalNames, Description, MainPicture, Names, PVs, Tags, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a list of entry names. Ideal for autocomplete boxes.

*Tags:* `EntryApi`

#### Input Parameters
* `query` - _optional_ - Text query.
* `nameMatchMode` - _optional_ - Name match mode.
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `maxResults` - _optional_ - Maximum number of results.

### Gets a list of PVs for songs.

*Tags:* `PVApi`

#### Input Parameters
* `author` - _optional_ - Uploader name (optional).
* `maxResults` - _optional_ - Maximum number of results.
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a page of event series.

*Tags:* `ReleaseEventSeriesApi`

#### Input Parameters
* `query` - _optional_ - Text query.
* `start` - _optional_ - First item to be retrieved (optional).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional).
* `nameMatchMode` - _optional_ - Match mode for event name (optional).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Deletes an event series.

*Tags:* `ReleaseEventSeriesApi`

#### Input Parameters
* `id` - _required_ - ID of the series to be deleted.
* `notes` - _optional_ - Notes.
* `hardDelete` - _optional_ - If true, the entry is hard deleted. Hard deleted entries cannot be restored normally, but they will be moved to trash.
            If false, the entry is soft deleted, meaning it can still be restored.

### Gets a page of events.

*Tags:* `ReleaseEventApi`

#### Input Parameters
* `query` - _optional_ - Event name query (optional).
* `nameMatchMode` - _optional_ - Match mode for event name (optional, defaults to Auto).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `seriesId` - _optional_ - Filter by series Id.
* `afterDate` - _optional_ - Filter by events after this date (inclusive).
* `beforeDate` - _optional_ - Filter by events before this date (exclusive).
* `category` - _optional_ - Filter by event category.
    Possible values: Unspecified, AlbumRelease, Anniversary, Club, Concert, Contest, Convention, Other.
* `userCollectionId` - _optional_ - Filter to include only events in user's events (interested or attending).
* `tagId` - _optional_ - Filter by one or more tag Ids (optional).
* `childTags` - _optional_ - Include child tags, if the tags being filtered by have any.
* `artistId` - _optional_ - Filter by artist Id.
* `childVoicebanks` - _optional_ - Include child voicebanks, if the artist being filtered by has any.
* `includeMembers` - _optional_ - Include members of groups. This applies if {artistId} is a group.
* `status` - _optional_ - Filter by entry status.
    Possible values: Draft, Finished, Approved, Locked.
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - Sort rule (optional, defaults to Name). 
            Possible values are None, Name, Date, SeriesName.
    Possible values: None, Name, Date, AdditionDate, SeriesName.
* `fields` - _optional_ - Optional fields (optional). Possible values are Description, Series.
    Possible values: None, AdditionalNames, Artists, Description, MainPicture, Names, Series, SongList, WebLinks.
* `lang` - _optional_ - Content language preference.
    Possible values: Default, Japanese, Romaji, English.

### Find event names by a part of name.<br/>
>             <br/>
>             Matching is done anywhere from the name.

*Tags:* `ReleaseEventApi`

#### Input Parameters
* `query` - _optional_ - Event name query, for example "Voc@loid".
* `maxResults` - _optional_ - Maximum number of search results.

### Gets a list of albums for a specific event.

*Tags:* `ReleaseEventApi`

#### Input Parameters
* `eventId` - _required_ - Release event ID.
* `fields` - _optional_ - List of optional album fields.
    Possible values: None, AdditionalNames, Artists, Description, Discs, Identifiers, MainPicture, Names, PVs, ReleaseEvent, Tags, Tracks, WebLinks.
* `lang` - _optional_ - Content language preference.
    Possible values: Default, Japanese, Romaji, English.

### Gets a list of songs for a specific event.

*Tags:* `ReleaseEventApi`

#### Input Parameters
* `eventId` - _required_ - Event ID.
* `fields` - _optional_ - List of optional song fields.
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `lang` - _optional_ - Content language preference.
    Possible values: Default, Japanese, Romaji, English.

### Creates a new report.

*Tags:* `ReleaseEventApi`

#### Input Parameters
* `eventId` - _required_ - Event to be reported.
* `reportType` - _required_ - Report type.
    Possible values: InvalidInfo, Duplicate, Inappropriate, Other.
* `notes` - _required_ - Notes. Optional.
* `versionNumber` - _required_ - Version to be reported. Optional.

### Deletes an event.

*Tags:* `ReleaseEventApi`

#### Input Parameters
* `id` - _required_ - ID of the event to be deleted.
* `notes` - _optional_ - Notes.
* `hardDelete` - _optional_ - If true, the entry is hard deleted. Hard deleted entries cannot be restored normally, but they will be moved to trash.
            If false, the entry is soft deleted, meaning it can still be restored.

### ReleaseEventApi_GetOne

*Tags:* `ReleaseEventApi`

#### Input Parameters
* `id` - _required_
* `fields` - _optional_
    Possible values: None, AdditionalNames, Artists, Description, MainPicture, Names, Series, SongList, WebLinks.
* `lang` - _optional_
    Possible values: Default, Japanese, Romaji, English.

### Gets a number of resource sets for a specific culture.

*Tags:* `ResourcesApi`

#### Input Parameters
* `cultureCode` - _required_ - Culture code, for example "en-US" or "fi-FI".
* `setNames` - _required_ - Names of resource sets to be returned. More than one value can be specified. For example "artistTypeNames"

### Creates a song list.

*Tags:* `SongListApi`

### Deletes a comment.

> Normal users can delete their own comments, moderators can delete all comments.<br/>
>             Requires login.

*Tags:* `SongListApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be deleted.

### Updates a comment.

> Normal users can edit their own comments, moderators can edit all comments.<br/>
>             Requires login.

*Tags:* `SongListApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be edited.

### Gets a list of featured song lists.

*Tags:* `SongListApi`

#### Input Parameters
* `query` - _optional_ - Song list name query (optional).
* `nameMatchMode` - _optional_ - Match mode for list name (optional, defaults to Auto).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `featuredCategory` - _optional_ - Filter by a specific featured category. If empty, all categories are returned.
    Possible values: Nothing, Concerts, VocaloidRanking, Pools, Other.
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 50).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - List sort rule. Possible values are Nothing, Date, CreateDate, Name.
    Possible values: None, Name, Date, CreateDate.

### Gets a list of featuedd list names. Ideal for autocomplete boxes.

*Tags:* `SongListApi`

#### Input Parameters
* `query` - _optional_ - Text query.
* `nameMatchMode` - _optional_ - Name match mode. Words is treated the same as Partial.
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `featuredCategory` - _optional_ - Filter by a specific featured category. If empty, all categories are returned.
    Possible values: Nothing, Concerts, VocaloidRanking, Pools, Other.
* `maxResults` - _optional_ - Maximum number of results.

### Deletes a song list.

*Tags:* `SongListApi`

#### Input Parameters
* `id` - _required_ - ID of the list to be deleted.
* `notes` - _optional_ - Notes.
* `hardDelete` - _optional_ - If true, the entry is hard deleted. Hard deleted entries cannot be restored normally, but they will be moved to trash.
            If false, the entry is soft deleted, meaning it can still be restored.

### Gets a list of comments for a song list.

*Tags:* `SongListApi`

#### Input Parameters
* `listId` - _required_ - ID of the list whose comments to load.

### Posts a new comment.

*Tags:* `SongListApi`

#### Input Parameters
* `listId` - _required_ - ID of the song list for which to create the comment.

### Gets a list of songs in a song list.

*Tags:* `SongListApi`

#### Input Parameters
* `listId` - _required_ - ID of the song list.
* `query` - _optional_ - Song name query (optional).
* `songTypes` - _optional_ - Filtered song types (optional).
* `pvServices` - _optional_ - Filter by one or more PV services (separated by commas). The song will pass the filter if it has a PV for any of the matched services.
    Possible values: Nothing, NicoNicoDouga, Youtube, SoundCloud, Vimeo, Piapro, Bilibili, File, LocalFile, Creofuga.
* `tagId` - _optional_ - Filter by one or more tag Ids (optional).
* `artistId` - _optional_ - Filter by artist Id.
* `childVoicebanks` - _optional_ - Include child voicebanks, if the artist being filtered by has any.
* `advancedFilters` - _optional_ - List of advanced filters (optional).
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 50).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - Song sort rule (optional, by default songs are sorted by song list order).
    Possible values: None, Name, AdditionDate, PublishDate, FavoritedTimes, RatingScore.
* `nameMatchMode` - _optional_ - Match mode for song name (optional, defaults to Auto).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `fields` - _optional_ - List of optional fields (optional). Possible values are Albums, Artists, Names, PVs, Tags, ThumbUrl, WebLinks.
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Find songs.

*Tags:* `SongApi`

#### Input Parameters
* `query` - _optional_ - Song name query (optional).
* `songTypes` - _optional_ - Filtered song types (optional). 
            Possible values are Original, Remaster, Remix, Cover, Instrumental, Mashup, MusicPV, DramaPV, Other.
* `tagName` - _optional_ - Filter by one or more tag names (optional).
* `tagId` - _optional_ - Filter by one or more tag Ids (optional).
* `childTags` - _optional_ - Include child tags, if the tags being filtered by have any.
* `artistId` - _optional_ - Filter by artist Id.
* `artistParticipationStatus` - _optional_ - Filter by artist participation status. Only valid if artistId is specified.
            Everything (default): Show all songs by that artist (no filter).
            OnlyMainAlbums: Show only main songs by that artist.
            OnlyCollaborations: Show only collaborations by that artist.
    Possible values: Everything, OnlyMainAlbums, OnlyCollaborations.
* `childVoicebanks` - _optional_ - Include child voicebanks, if the artist being filtered by has any.
* `includeMembers` - _optional_ - Include members of groups. This applies if {artistId} is a group.
* `onlyWithPvs` - _optional_ - Whether to only include songs with at least one PV.
* `pvServices` - _optional_ - Filter by one or more PV services (separated by commas). The song will pass the filter if it has a PV for any of the matched services.
    Possible values: Nothing, NicoNicoDouga, Youtube, SoundCloud, Vimeo, Piapro, Bilibili, File, LocalFile, Creofuga.
* `since` - _optional_ - Allow only entries that have been created at most this many hours ago. By default there is no filtering.
* `minScore` - _optional_ - Minimum rating score. Optional.
* `userCollectionId` - _optional_ - Filter by user's rated songs. By default there is no filtering.
* `releaseEventId` - _optional_ - Filter by release event. By default there is no filtering.
* `status` - _optional_ - Filter by entry status (optional).
    Possible values: Draft, Finished, Approved, Locked.
* `advancedFilters` - _optional_ - List of advanced filters (optional).
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 50).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - Sort rule (optional, defaults to Name). Possible values are None, Name, AdditionDate, FavoritedTimes, RatingScore.
    Possible values: None, Name, AdditionDate, PublishDate, FavoritedTimes, RatingScore.
* `preferAccurateMatches` - _optional_ - Whether the search should prefer accurate matches. 
            If this is true, entries that match by prefix will be moved first, instead of being sorted alphabetically.
            Requires a text query. Does not support pagination.
            This is mostly useful for autocomplete boxes.
* `nameMatchMode` - _optional_ - Match mode for song name (optional, defaults to Exact).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `fields` - _optional_ - List of optional fields (optional). Possible values are Albums, Artists, Names, PVs, Tags, ThumbUrl, WebLinks.
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a song by PV.

*Tags:* `SongApi`

#### Input Parameters
* `pvService` - _required_ - PV service (required). Possible values are NicoNicoDouga, Youtube, SoundCloud, Vimeo, Piapro, Bilibili.
    Possible values: NicoNicoDouga, Youtube, SoundCloud, Vimeo, Piapro, Bilibili, File, LocalFile, Creofuga.
* `pvId` - _required_ - PV Id (required). For example sm123456.
* `fields` - _optional_ - List of optional fields (optional). Possible values are Albums, Artists, Names, PVs, Tags, ThumbUrl, WebLinks.
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Deletes a comment.

> Normal users can delete their own comments, moderators can delete all comments.<br/>
>             Requires login.

*Tags:* `SongApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be deleted.

### Updates a comment.

> Normal users can edit their own comments, moderators can edit all comments.<br/>
>             Requires login.

*Tags:* `SongApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be edited.

### Gets list of highlighted songs, same as front page.

> Output is cached for 1 hour.

*Tags:* `SongApi`

#### Input Parameters
* `languagePreference` - _optional_
    Possible values: Default, Japanese, Romaji, English.
* `fields` - _optional_
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.

### Gets lyrics by ID.

> Output is cached. Specify song version as parameter to refresh.

*Tags:* `SongApi`

#### Input Parameters
* `lyricsId` - _required_ - Lyrics ID.

### Gets a list of song names. Ideal for autocomplete boxes.

*Tags:* `SongApi`

#### Input Parameters
* `query` - _optional_ - Text query.
* `nameMatchMode` - _optional_ - Name match mode.
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `maxResults` - _optional_ - Maximum number of results.

### Gets top rated songs.

*Tags:* `SongApi`

#### Input Parameters
* `durationHours` - _optional_ - Duration in hours from which to get songs.
* `startDate` - _optional_ - Lower bound of the date. Optional.
* `filterBy` - _optional_ - Filtering mode.
    Possible values: CreateDate, PublishDate, Popularity.
* `vocalist` - _optional_ - Vocalist selection.
    Possible values: Nothing, Vocaloid, UTAU, CeVIO.
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional).
* `fields` - _optional_ - Optional song fields to load.
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `languagePreference` - _optional_ - Language preference.
    Possible values: Default, Japanese, Romaji, English.

### Deletes a song.

*Tags:* `SongApi`

#### Input Parameters
* `id` - _required_ - ID of the song to be deleted.
* `notes` - _optional_ - Notes.

### Gets a song by Id.

*Tags:* `SongApi`

#### Input Parameters
* `id` - _required_ - Song Id (required).
* `fields` - _optional_ - List of optional fields (optional). 
            Possible values are Albums, Artists, Names, PVs, Tags, ThumbUrl, WebLinks.
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a list of comments for a song.

> Pagination and sorting might be added later.

*Tags:* `SongApi`

#### Input Parameters
* `id` - _required_ - ID of the song whose comments to load.

### Posts a new comment.

*Tags:* `SongApi`

#### Input Parameters
* `id` - _required_ - ID of the song for which to create the comment.

### Gets derived (alternate versions) of a song.

> Pagination and sorting might be added later.

*Tags:* `SongApi`

#### Input Parameters
* `id` - _required_ - Song Id (required).
* `fields` - _optional_ - List of optional fields (optional). 
            Possible values are Albums, Artists, Names, PVs, Tags, ThumbUrl, WebLinks.
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Get ratings for a song.

> The result includes ratings and user information.<br/>
>             For users who have requested not to make their ratings public, the user will be empty.

*Tags:* `SongApi`

#### Input Parameters
* `id` - _required_ - Song ID.
* `userFields` - _required_ - Optional fields for the users.
    Possible values: None, KnownLanguages, MainPicture, OldUsernames.
* `lang` - _optional_ - Content language preference.
    Possible values: Default, Japanese, Romaji, English.

### Add or update rating for a specific song, for the currently logged in user.

> If the user has already rated the song, any previous rating is replaced.<br/>
>             Authorization cookie must be included.<br/>
>             This API supports CORS.

*Tags:* `SongApi`

#### Input Parameters
* `id` - _required_ - ID of the song to be rated.

### Gets related songs.

*Tags:* `SongApi`

#### Input Parameters
* `id` - _required_ - Song whose related songs are to be queried.
* `fields` - _optional_ - Optional song fields.
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `lang` - _optional_ - Content language preference.
    Possible values: Default, Japanese, Romaji, English.

### Find tags.

*Tags:* `TagApi`

#### Input Parameters
* `query` - _optional_ - Tag name query (optional).
* `allowChildren` - _optional_ - Whether to allow child tags. If this is false, only root tags (that aren't children of any other tag) will be included.
* `categoryName` - _optional_ - Filter tags by category (optional). If specified, this must be an exact match (case insensitive).
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 30).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `nameMatchMode` - _optional_ - Match mode for song name (optional, defaults to Exact).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `sort` - _optional_ - Sort rule (optional, by default tags are sorted by name).Possible values are Name and UsageCount.
    Possible values: Nothing, Name, AdditionDate, UsageCount.
* `preferAccurateMatches` - _optional_ - Whether the search should prefer accurate matches. 
            If this is true, entries that match by prefix will be moved first, instead of being sorted alphabetically.
            Requires a text query. Does not support pagination.
            This is mostly useful for autocomplete boxes.
* `fields` - _optional_ - List of optional fields (optional).
    Possible values: None, AdditionalNames, AliasedTo, Description, MainPicture, Names, Parent, RelatedTags, TranslatedDescription, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.
* `target` - _optional_
    Possible values: Nothing, Album, Artist, AlbumArtist, Event, Song, AlbumSong, ArtistSong, All.

### Creates a new tag.

*Tags:* `TagApi`

#### Input Parameters
* `name` - _required_ - Tag English name. Tag names must be unique.

### DEPRECATED. Gets a tag by name.

*Tags:* `TagApi`

#### Input Parameters
* `name` - _required_ - Tag name (required).
* `fields` - _optional_ - List of optional fields (optional).
    Possible values: None, AdditionalNames, AliasedTo, Description, MainPicture, Names, Parent, RelatedTags, TranslatedDescription, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a list of tag category names.

*Tags:* `TagApi`

#### Input Parameters
* `query` - _optional_
* `nameMatchMode` - _optional_
    Possible values: Auto, Partial, StartsWith, Exact, Words.

### Deletes a comment.<br/>
>             Normal users can delete their own comments, moderators can delete all comments.<br/>
>             Requires login.

*Tags:* `TagApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be deleted.

### Updates a comment.<br/>
>             Normal users can edit their own comments, moderators can edit all comments.<br/>
>             Requires login.

*Tags:* `TagApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be edited.

### Find tag names by a part of name.<br/>
>             <br/>
>             Matching is done anywhere from the name.

*Tags:* `TagApi`

#### Input Parameters
* `query` - _optional_ - Tag name query, for example "rock".
* `allowAliases` - _optional_ - Whether to find tags that are aliases of other tags as well. 
            If false, only tags that are not aliases will be listed.
* `maxResults` - _optional_ - Maximum number of search results.

### Gets the most common tags in a category.

*Tags:* `TagApi`

#### Input Parameters
* `categoryName` - _optional_ - Tag category, for example "Genres". Optional - if not specified, no filtering is done.
* `maxResults` - _optional_ - Maximum number of tags to return.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Deletes a tag.

*Tags:* `TagApi`

#### Input Parameters
* `id` - _required_ - ID of the tag to be deleted.
* `notes` - _optional_ - Notes (optional).
* `hardDelete` - _optional_ - If true, the entry is hard deleted. Hard deleted entries cannot be restored normally, but they will be moved to trash.
            If false, the entry is soft deleted, meaning it can still be restored.

### Gets a tag by ID.

*Tags:* `TagApi`

#### Input Parameters
* `id` - _required_ - Tag ID (required).
* `fields` - _optional_ - List of optional fields (optional).
    Possible values: None, AdditionalNames, AliasedTo, Description, MainPicture, Names, Parent, RelatedTags, TranslatedDescription, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a list of child tags for a tag.<br/>
>             Only direct children will be included.

*Tags:* `TagApi`

#### Input Parameters
* `tagId` - _required_ - ID of the tag whose children to load.
* `fields` - _optional_ - List of optional fields (optional).
    Possible values: None, AdditionalNames, AliasedTo, Description, MainPicture, Names, Parent, RelatedTags, TranslatedDescription, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a list of comments for a tag.<br/>
>             Note: pagination and sorting might be added later.

*Tags:* `TagApi`

#### Input Parameters
* `tagId` - _required_ - ID of the tag whose comments to load.

### Posts a new comment.

*Tags:* `TagApi`

#### Input Parameters
* `tagId` - _required_ - ID of the tag for which to create the comment.

### Creates a new report.

*Tags:* `TagApi`

#### Input Parameters
* `tagId` - _required_ - Tag to be reported.
* `reportType` - _required_ - Report type.
    Possible values: InvalidInfo, Duplicate, Inappropriate, Other.
* `notes` - _required_ - Notes. Optional.
* `versionNumber` - _required_ - Version to be reported. Optional.

### Gets a list of users.

*Tags:* `UserApi`

#### Input Parameters
* `query` - _optional_ - User name query (optional).
* `groups` - _optional_ - Filter by user group. Only one value supported for now. Optional.
    Possible values: Nothing, Limited, Regular, Trusted, Moderator, Admin.
* `joinDateAfter` - _optional_ - Filter by users who joined after this date (inclusive).
* `joinDateBefore` - _optional_ - Filter by users who joined before this date (exclusive).
* `nameMatchMode` - _optional_ - Name match mode.
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `start` - _optional_ - Index of the first entry to be loaded.
* `maxResults` - _optional_ - Maximum number of results to be loaded.
* `getTotalCount` - _optional_ - Whether to get total number of results.
* `sort` - _optional_ - Sort rule.
    Possible values: RegisterDate, Name, Group.
* `includeDisabled` - _optional_ - Whether to include disabled user accounts.
* `onlyVerified` - _optional_ - Whether to only include verified artists.
* `knowsLanguage` - _optional_ - Filter by known language (optional). This is the ISO 639-1 language code, for example "en" or "zh".
* `fields` - _optional_ - Optional fields. Possible values are None and MainPicture. Optional.
    Possible values: None, KnownLanguages, MainPicture, OldUsernames.

### Gets information about the currently logged in user.

> Requires login information.<br/>
>             This API supports CORS, and is restricted to specific origins.

*Tags:* `UserApi`

#### Input Parameters
* `fields` - _optional_ - Optional fields.
    Possible values: None, KnownLanguages, MainPicture, OldUsernames.

### Add or update collection status, media type and rating for a specific album, for the currently logged in user.

> If the user has already rated the album, any previous rating is replaced.<br/>
>             Authorization cookie must be included.

*Tags:* `UserApi`

#### Input Parameters
* `albumId` - _required_ - ID of the album to be rated.
* `collectionStatus` - _required_ - Collection status. Possible values are Nothing, Wishlisted, Ordered and Owned.
    Possible values: Nothing, Wishlisted, Ordered, Owned.
* `mediaType` - _required_ - Album media type. Possible values are PhysicalDisc, DigitalDownload and Other.
    Possible values: PhysicalDisc, DigitalDownload, Other.
* `rating` - _required_ - Rating to be given. Possible values are between 0 and 5.

### UserApi_DeleteFollowedTag

*Tags:* `UserApi`

#### Input Parameters
* `tagId` - _required_

### UserApi_PostFollowedTag

*Tags:* `UserApi`

#### Input Parameters
* `tagId` - _required_

### Gets currently logged in user's rating for a song.

> Requires authentication.

*Tags:* `UserApi`

#### Input Parameters
* `songId` - _required_ - ID of the song whose rating is to be checked.

### Refresh entry edit status, indicating that the current user is still editing that entry.

*Tags:* `UserApi`

#### Input Parameters
* `entryType` - _required_ - Type of entry.
    Possible values: Undefined, Album, Artist, DiscussionTopic, PV, ReleaseEvent, ReleaseEventSeries, Song, SongList, Tag, User.
* `entryId` - _required_ - Entry ID.

### Appends tags for a song, by the currently logged in user.

> This can only be used to add tags - existing tags will not be removed. <br/>
>             Nothing will be done for tags that are already applied by the current user for the song.<br/>
>             Authorization cookie is required.

*Tags:* `UserApi`

#### Input Parameters
* `songId` - _required_ - ID of the song to be tagged.

### Gets a user message.

> The message will be marked as read.<br/>
>             User can only load messages from their own inbox.

*Tags:* `UserApi`

#### Input Parameters
* `messageId` - _required_ - ID of the message.

### Gets a list of user names. Ideal for autocomplete boxes.

*Tags:* `UserApi`

#### Input Parameters
* `query` - _optional_ - Text query.
* `nameMatchMode` - _optional_ - Name match mode. Words is treated the same as Partial.
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `maxResults` - _optional_ - Maximum number of results.
* `includeDisabled` - _optional_ - Whether to include disabled user accounts. If false, disabled accounts are excluded.

### Deletes a comment.

> Normal users can delete their own comments, moderators can delete all comments.<br/>
>             Requires login.

*Tags:* `UserApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be deleted.

### Updates a comment.

> Normal users can edit their own comments, moderators can edit all comments.<br/>
>             Requires login.

*Tags:* `UserApi`

#### Input Parameters
* `commentId` - _required_ - ID of the comment to be edited.

### Gets user by ID.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - User ID.
* `fields` - _optional_ - Optional fields.
    Possible values: None, KnownLanguages, MainPicture, OldUsernames.

### Gets a list of albums in a user's collection.

> This includes albums that have been rated by the user as well as albums that the user has bought or wishlisted.<br/>
>             Note that the user might have set his album ownership status and media type as private, in which case those properties are not included.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - ID of the user whose albums are to be browsed.
* `query` - _optional_ - Album name query (optional).
* `tagId` - _optional_ - Filter by tag Id (optional).
* `tag` - _optional_ - Filter by tag (optional).
* `artistId` - _optional_ - Filter by album artist (optional).
* `purchaseStatuses` - _optional_ - Filter by a comma-separated list of purchase statuses (optional). Possible values are Nothing, Wishlisted, Ordered, Owned, and all combinations of these.
    Possible values: Nothing, Wishlisted, Ordered, Owned, All.
* `releaseEventId` - _optional_ - Filter by release event. Optional.
* `albumTypes` - _optional_ - Filter by album type (optional).
    Possible values: Unknown, Album, Single, EP, SplitAlbum, Compilation, Video, Artbook, Game, Fanmade, Instrumental, Other.
* `advancedFilters` - _optional_ - List of advanced filters (optional).
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 50).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - Sort rule (optional, defaults to Name). Possible values are None, Name, ReleaseDate, AdditionDate, RatingAverage, RatingTotal, CollectionCount.
    Possible values: None, Name, ReleaseDate, ReleaseDateWithNulls, AdditionDate, RatingAverage, RatingTotal, NameThenReleaseDate, CollectionCount.
* `nameMatchMode` - _optional_ - Match mode for album name (optional, defaults to Auto).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `fields` - _optional_ - List of optional fields (optional). Possible values are Artists, MainPicture, Names, PVs, Tags, WebLinks.
    Possible values: None, AdditionalNames, Artists, Description, Discs, Identifiers, MainPicture, Names, PVs, ReleaseEvent, Tags, Tracks, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a list of events a user has subscribed to.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - User ID.
* `relationshipType` - _required_ - Type of event subscription.
    Possible values: Interested, Attending.

### Gets a list of artists followed by a user.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - ID of the user whose followed artists are to be browsed.
* `query` - _optional_ - Artist name query (optional).
* `artistType` - _optional_ - Filter by artist type.
    Possible values: Unknown, Circle, Label, Producer, Animator, Illustrator, Lyricist, Vocaloid, UTAU, CeVIO, OtherVoiceSynthesizer, OtherVocalist, OtherGroup, OtherIndividual, Utaite, Band, Vocalist, Character.
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 50).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - Sort rule (optional, defaults to Name). Possible values are None, Name, AdditionDate, AdditionDateAsc.
    Possible values: None, Name, AdditionDate, AdditionDateAsc, ReleaseDate, SongCount, SongRating, FollowerCount.
* `nameMatchMode` - _optional_ - Match mode for artist name (optional, defaults to Auto).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `fields` - _optional_ - List of optional fields (optional). Possible values are Description, Groups, Members, Names, Tags, WebLinks.
    Possible values: None, AdditionalNames, ArtistLinks, ArtistLinksReverse, BaseVoicebank, Description, MainPicture, Names, Tags, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Deletes a list of user messages.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - ID of the user whose messages to delete.
* `messageId` - _required_ - IDs of messages.

### Gets a list of messages.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - User ID. Must be the currently logged in user (loading messages for another user is not allowed).
* `inbox` - _optional_ - Type of inbox. Possible values are Nothing (load all, default), Received, Sent, Notifications.
    Possible values: Nothing, Received, Sent, Notifications.
* `unread` - _optional_ - Whether to only load unread messages. Loading unread messages is only possible for received messages and notifications (not sent messages).
* `anotherUserId` - _optional_ - Filter by id of the other user (either sender or receiver).
* `start` - _optional_ - Index of the first entry to be loaded.
* `maxResults` - _optional_ - Maximum number of results to be loaded.
* `getTotalCount` - _optional_ - Whether to get total number of results.

### Creates a new message.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - User ID. Must be logged in user.

### Gets a list of comments posted on user's profile.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - ID of the user whose comments are to be retrieved.
* `start` - _optional_ - Index of the first comment to be loaded.
* `maxResults` - _optional_ - Maximum number of comments to load.
* `getTotalCount` - _optional_ - Whether to load the total number of comments.

### Posts a new comment.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - ID of the user for whom to create the comment.

### Gets a list of songs rated by a user.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - ID of the user whose songs are to be browsed.
* `query` - _optional_ - Song name query (optional).
* `tagName` - _optional_ - Filter by tag name (optional).
* `tagId` - _optional_ - Filter by tag Id (optional). This filter can be specified multiple times.
* `artistId` - _optional_ - Filter by song artist (optional).
* `childVoicebanks` - _optional_ - Include child voicebanks, if the artist being filtered by has any.
* `artistGrouping` - _optional_ - Logical grouping for artists.
    Possible values: And, Or.
* `rating` - _optional_ - Filter songs by given rating (optional).
    Possible values: Nothing, Dislike, Like, Favorite.
* `songListId` - _optional_ - Filter songs by song list (optional).
* `groupByRating` - _optional_ - Group results by rating so that highest rated are first.
* `pvServices` - _optional_ - Filter by one or more PV services (separated by commas). The song will pass the filter if it has a PV for any of the matched services.
    Possible values: Nothing, NicoNicoDouga, Youtube, SoundCloud, Vimeo, Piapro, Bilibili, File, LocalFile, Creofuga.
* `advancedFilters` - _optional_ - List of advanced filters (optional).
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 50).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - Sort rule (optional, defaults to Name). Possible values are None, Name, AdditionDate, FavoritedTimes, RatingScore.
    Possible values: None, Name, AdditionDate, PublishDate, FavoritedTimes, RatingScore, RatingDate.
* `nameMatchMode` - _optional_ - Match mode for song name (optional, defaults to Auto).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `fields` - _optional_ - List of optional fields (optional). Possible values are Albums, Artists, Names, PVs, Tags, ThumbUrl, WebLinks.
    Possible values: None, AdditionalNames, Albums, Artists, Lyrics, MainPicture, Names, PVs, ReleaseEvent, Tags, ThumbUrl, WebLinks.
* `lang` - _optional_ - Content language preference (optional).
    Possible values: Default, Japanese, Romaji, English.

### Gets a specific user's rating for a song.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - User whose rating is to be checked.
* `songId` - _required_ - ID of the song whose rating is to be checked.

### Updates user setting.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - ID of the user to be updated. This must match the current user OR be unspecified (or 0) if the user is not logged in.
* `settingName` - _required_ - Name of the setting to be updated, for example 'showChatBox'.

### Gets a list of song lists for a user.

*Tags:* `UserApi`

#### Input Parameters
* `id` - _required_ - User whose song lists are to be loaded.
* `query` - _optional_ - Song list name query (optional).
* `nameMatchMode` - _optional_ - Match mode for song name (optional, defaults to Auto).
    Possible values: Auto, Partial, StartsWith, Exact, Words.
* `start` - _optional_ - First item to be retrieved (optional, defaults to 0).
* `maxResults` - _optional_ - Maximum number of results to be loaded (optional, defaults to 10, maximum of 50).
* `getTotalCount` - _optional_ - Whether to load total number of items (optional, default to false).
* `sort` - _optional_ - Sort option for the song lists. Possible values are None, Name, Date, CreateDate. Default is Name.
    Possible values: None, Name, Date, CreateDate.
* `fields` - _optional_ - List of optional fields.
    Possible values: None, Description, MainPicture.

## License

**flow**ground :- Telekom iPaaS / vocadb-net-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
