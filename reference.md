# Reference
<details><summary><code>client.CreateInitialSuperadmin(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebPasswordAuthResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create the first superadmin user. Only works when no admin exists.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostSetupRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.CreateInitialSuperadmin(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostSetupRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.CheckSystemSetupStatus() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return whether the system has been initialized with a superadmin user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.CheckSystemSetupStatus(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## BugReports
<details><summary><code>client.BugReports.ListAllBugReports() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalBugreportsInternalDomainBugReport</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return paginated list of all bug reports. Supports filtering by status and domain label.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAdminBugReportsRequest{}
client.BugReports.ListAllBugReports(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**status:** `*string` — Filter by status (pending, reviewed, published, closed)
    
</dd>
</dl>

<dl>
<dd>

**domain:** `*string` — Filter by domain label (chat, admin, ...)
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Max results (default 20, max 100)
    
</dd>
</dl>

<dl>
<dd>

**offset:** `*int` — Page offset
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BugReports.GetBugReportByID(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalBugreportsInternalDomainBugReport</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return full detail of a single bug report including DOM element info and review notes.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAdminBugReportsIDRequest{
        ID: 1,
    }
client.BugReports.GetBugReportByID(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Bug report ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BugReports.UpdateBugReport(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalBugreportsInternalDomainBugReport</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update status and review notes. Status transitions: pending->reviewed, pending->closed, reviewed->published, reviewed->closed, published->closed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PatchAdminBugReportsIDRequest{
        ID: 1,
        Body: &mktsdkgo.PatchAdminBugReportsIDRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.BugReports.UpdateBugReport(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Bug report ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PatchAdminBugReportsIDRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BugReports.PublishBugReportToGitHub(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a GitHub Issue from a reviewed bug report with structured markdown body and auto-detected domain labels.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAdminBugReportsIDPublishRequest{
        ID: 1,
    }
client.BugReports.PublishBugReportToGitHub(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Bug report ID (must be in reviewed status)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BugReports.SubmitBugReport(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Submit a bug report with DOM context (element info, viewport). The report is stored with status "pending" for admin review.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostBugReportsRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.BugReports.SubmitBugReport(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostBugReportsRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BugReports.ListMyBugReports() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalBugreportsInternalDomainBugReport</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return paginated list of bug reports submitted by the authenticated user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetBugReportsMineRequest{}
client.BugReports.ListMyBugReports(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*int` — Max results (default 20, max 100)
    
</dd>
</dl>

<dl>
<dd>

**offset:** `*int` — Page offset
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## AdminBulletins
<details><summary><code>client.AdminBulletins.ListAllBulletinsAdmin() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalBulletinInternalDomainBulletin</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return a paginated list of all bulletins including drafts, with optional filters. Requires admin role.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAdminBulletinsRequest{}
client.AdminBulletins.ListAllBulletinsAdmin(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**type_:** `*string` — Filter by type
    
</dd>
</dl>

<dl>
<dd>

**category:** `*string` — Filter by category
    
</dd>
</dl>

<dl>
<dd>

**section:** `*string` — Filter by section
    
</dd>
</dl>

<dl>
<dd>

**version:** `*string` — Filter by version
    
</dd>
</dl>

<dl>
<dd>

**includeArchived:** `*bool` — Include archived bulletins
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Max results
    
</dd>
</dl>

<dl>
<dd>

**cursorVal:** `*int` — Cursor value for pagination
    
</dd>
</dl>

<dl>
<dd>

**cursorID:** `*int` — Cursor ID for pagination
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.AdminBulletins.CreateANewBulletin(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalBulletinInternalDomainBulletin</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new announcement, changelog, or doc. Requires admin role.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAdminBulletinsRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.AdminBulletins.CreateANewBulletin(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostAdminBulletinsRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.AdminBulletins.GetBulletinByIDAdmin(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalBulletinInternalDomainBulletin</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return any bulletin by ID including drafts and expired ones. Requires admin role.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAdminBulletinsIDRequest{
        ID: 1,
    }
client.AdminBulletins.GetBulletinByIDAdmin(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Bulletin ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.AdminBulletins.UpdateABulletin(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalBulletinInternalDomainBulletin</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update an existing bulletin's content or metadata. Requires admin role.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PutAdminBulletinsIDRequest{
        ID: 1,
        Body: &mktsdkgo.PutAdminBulletinsIDRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.AdminBulletins.UpdateABulletin(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Bulletin ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PutAdminBulletinsIDRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.AdminBulletins.DeleteABulletin(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a draft bulletin. Requires admin role.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteAdminBulletinsIDRequest{
        ID: 1,
    }
client.AdminBulletins.DeleteABulletin(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Bulletin ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.AdminBulletins.ArchiveABulletin(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Archive a published or draft bulletin. Requires admin role.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAdminBulletinsIDArchiveRequest{
        ID: 1,
    }
client.AdminBulletins.ArchiveABulletin(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Bulletin ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.AdminBulletins.PublishABulletin(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Publish a draft bulletin to make it visible to users. Requires admin role.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAdminBulletinsIDPublishRequest{
        ID: 1,
    }
client.AdminBulletins.PublishABulletin(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Bulletin ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Files
<details><summary><code>client.Files.ListFilesInDirectory() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayInternalFilesInternalWebFileResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List files in the specified business directory
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAdminFilesRequest{}
client.Files.ListFilesInDirectory(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**bizID:** `*string` — Business context ID
    
</dd>
</dl>

<dl>
<dd>

**dirPath:** `*string` — Directory path, defaults to /
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Files.GetFile(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalFilesInternalWebFileResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get file metadata by ID
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAdminFilesIDRequest{
        ID: 1,
    }
client.Files.GetFile(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — File ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Files.DeleteFile(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalFilesInternalWebFileDeleteVo</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a file by ID
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteAdminFilesIDRequest{
        ID: 1,
    }
client.Files.DeleteFile(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — File ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Files.UpdateFile(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalFilesInternalWebFileResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update file name and/or visibility
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PatchAdminFilesIDRequest{
        ID: 1,
        Body: &mktsdkgo.PatchAdminFilesIDRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Files.UpdateFile(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — File ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PatchAdminFilesIDRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Files.GetDownloadURL(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalFilesInternalWebFileDownloadVo</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get a presigned download URL for a file
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAdminFilesIDDownloadRequest{
        ID: 1,
    }
client.Files.GetDownloadURL(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — File ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Files.IngestFileFromURL(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalFilesInternalWebFileResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Download a file from the given URL and store in the files domain
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAdminFilesIngestURLRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Files.IngestFileFromURL(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostAdminFilesIngestURLRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## AdminMarketplace
<details><summary><code>client.AdminMarketplace.TopResourcesRankingAdmin() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebTopResourcesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns top models ranked by call count or revenue. Only includes listed/published models.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAdminMarketplaceTopResourcesRequest{}
client.AdminMarketplace.TopResourcesRankingAdmin(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**sort:** `*string` — Sort field: calls (default) or revenue
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Max results (default 20, max 100)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## AdminRevenue
<details><summary><code>client.AdminRevenue.MarketplaceFeeRevenueSummary() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalPaymentsInternalDomainMarketplaceFeeSummary</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns total marketplace fees, breakdown by resource type and by seller. Requires admin role.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAdminRevenueFeesRequest{}
client.AdminRevenue.MarketplaceFeeRevenueSummary(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**period:** `*string` — Period: today, week, all (default all)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Admin
<details><summary><code>client.Admin.列出所有系统配置项() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxCodeResp</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

返回所有已知配置 key，DB 中有值的显示 DB 值（source=db），无值的显示代码默认值（source=default）
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Admin.列出所有系统配置项(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Admin.更新系统配置项(Key, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxCodeResp</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

更新指定 key 的系统配置值并清除该 key 的缓存
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PutAdminSysConfigKeyRequest{
        Key: "key",
        Body: &mktsdkgo.PutAdminSysConfigKeyRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Admin.更新系统配置项(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**key:** `string` — 配置键
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PutAdminSysConfigKeyRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Admin.重载系统配置缓存(Key, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxCodeResp</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

清除指定 key 的内存缓存，下次读取从 DB 加载最新值
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAdminSysConfigKeyReloadRequest{
        Key: "key",
        Body: map[string]any{
            "key": "value",
        },
    }
client.Admin.重载系统配置缓存(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**key:** `string` — 配置键
    
</dd>
</dl>

<dl>
<dd>

**request:** `map[string]any` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Comments
<details><summary><code>client.Comments.ListCommentsAdmin() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalCommentsInternalWebCommentListVo</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all comments for admin management. Requires session + admin auth.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAPIV1AdminCommentsRequest{
        TargetType: "target_type",
    }
client.Comments.ListCommentsAdmin(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**targetType:** `string` — Target type (article, etc.)
    
</dd>
</dl>

<dl>
<dd>

**status:** `*string` — Filter by status (pending, approved, rejected, hidden)
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*int` — Pagination cursor
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Page size (default 20, max 100)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Comments.ListComments() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalCommentsInternalWebCommentTreeVo</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the comment tree for a specific target
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAPIV1CommentsRequest{
        TargetType: "target_type",
        TargetID: 1,
    }
client.Comments.ListComments(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**targetType:** `string` — Target type (article, etc.)
    
</dd>
</dl>

<dl>
<dd>

**targetID:** `int` — Target ID
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*int` — Pagination cursor
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Page size (default 20, max 100)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Comments.CreateComment(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalCommentsInternalDomainComment</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new comment or reply. Requires session auth.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAPIV1CommentsRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Comments.CreateComment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostAPIV1CommentsRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Comments.UpdateComment(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalCommentsInternalDomainComment</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Edit a comment body. Only the author can edit.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PutAPIV1CommentsIDRequest{
        ID: 1,
        Body: &mktsdkgo.PutAPIV1CommentsIDRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Comments.UpdateComment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Comment ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PutAPIV1CommentsIDRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Comments.DeleteComment(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxCodeResp</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Soft-delete a comment. Author or admin can delete.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteAPIV1CommentsIDRequest{
        ID: 1,
    }
client.Comments.DeleteComment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Comment ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Notifications
<details><summary><code>client.Notifications.AdminSendNotification(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Send a notification to a specified user (admin only)
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAPIV1AdminNotificationsRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Notifications.AdminSendNotification(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostAPIV1AdminNotificationsRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Notifications.ListNotifications() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List the current user's notifications with cursor-based pagination
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAPIV1NotificationsRequest{}
client.Notifications.ListNotifications(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cursorID:** `*int` — Cursor ID for pagination
    
</dd>
</dl>

<dl>
<dd>

**cursorCreatedAt:** `*int` — Cursor created_at timestamp
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Page size (default 20, max 100)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Notifications.MarkNotificationAsRead(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Mark a single notification as read for the current user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAPIV1NotificationsIDReadRequest{
        ID: 1,
    }
client.Notifications.MarkNotificationAsRead(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Notification ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Notifications.ListPreferences() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List notification preferences for the current user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAPIV1NotificationsPreferencesRequest{}
client.Notifications.ListPreferences(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**channel:** `*string` — Filter by channel (in_app, email, sms)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Notifications.SetPreference(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Set a notification preference for the current user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PutAPIV1NotificationsPreferencesRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Notifications.SetPreference(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PutAPIV1NotificationsPreferencesRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Notifications.MarkAllAsRead() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Mark all notifications as read for the current user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Notifications.MarkAllAsRead(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Notifications.GetUnreadCount() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the count of unread notifications for the current user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Notifications.GetUnreadCount(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Payments
<details><summary><code>client.Payments.ListPaymentOrders() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all payment orders for the authenticated user with pagination
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAPIV1PaymentOrdersRequest{}
client.Payments.ListPaymentOrders(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number (default 1)
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Page size (default 20)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Payments.CreatePaymentOrder(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new top-up payment order with an optional product
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAPIV1PaymentOrdersRequest{
        Body: &mktsdkgo.PostAPIV1PaymentOrdersRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Payments.CreatePaymentOrder(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**deviceType:** `*string` — Device type: mobile, tablet, desktop, or unknown
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostAPIV1PaymentOrdersRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Payments.GetPaymentOrder(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a payment order by ID for the authenticated user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAPIV1PaymentOrdersIDRequest{
        ID: 1,
    }
client.Payments.GetPaymentOrder(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Order ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Wallets
<details><summary><code>client.Wallets.GetTransferDetail(TransferNo) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalPaymentsInternalWebWalletTransferV2Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the details of a wallet transfer by transfer number.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAPIV1PaymentWalletTransfersTransferNoRequest{
        TransferNo: 1,
    }
client.Wallets.GetTransferDetail(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**transferNo:** `int` — Transfer number
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wallets.ListWallets() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayInternalPaymentsInternalWebWalletV2Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all wallets for the current authenticated user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wallets.ListWallets(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wallets.GetWallet(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalPaymentsInternalWebWalletV2Response</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get a single wallet by ID with ownership verification.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAPIV1PaymentWalletsIDRequest{
        ID: 1,
    }
client.Wallets.GetWallet(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Wallet ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wallets.ConvertWalletCurrency(ID, request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Convert all balance from the source wallet to a target-currency wallet in-place, applying the exchange rate with markup. Idempotent via idempotency_key.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAPIV1PaymentWalletsIDConvertCurrencyRequest{
        ID: 1,
        Body: &mktsdkgo.PostAPIV1PaymentWalletsIDConvertCurrencyRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Wallets.ConvertWalletCurrency(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Source wallet ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostAPIV1PaymentWalletsIDConvertCurrencyRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wallets.ListWalletTransactions(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List paginated transactions for a specific wallet.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAPIV1PaymentWalletsIDTransactionsRequest{
        ID: 1,
    }
client.Wallets.ListWalletTransactions(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Wallet ID
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number (default 1)
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Items per page (default 20, max 100)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wallets.TransferBetweenWallets(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalPaymentsInternalWebWalletTransferEnvelope</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Transfer funds from the source wallet to another wallet belonging to the same user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAPIV1PaymentWalletsIDTransferRequest{
        ID: 1,
        Body: &mktsdkgo.PostAPIV1PaymentWalletsIDTransferRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Wallets.TransferBetweenWallets(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Source wallet ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostAPIV1PaymentWalletsIDTransferRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wallets.TransferRevenueWalletBalanceToMainWallet(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalPaymentsInternalWebWalletTransferEnvelope</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Transfer all balance from a revenue wallet to the user's main wallet. Only revenue wallets are eligible.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAPIV1PaymentWalletsIDTransferToMainRequest{
        ID: 1,
        Body: &mktsdkgo.PostAPIV1PaymentWalletsIDTransferToMainRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Wallets.TransferRevenueWalletBalanceToMainWallet(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Revenue wallet ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostAPIV1PaymentWalletsIDTransferToMainRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Auth
<details><summary><code>client.Auth.GenerateImageCaptcha() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebCaptchaGenerateResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Generate a CAPTCHA image and return the token plus base64-encoded PNG.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Auth.GenerateImageCaptcha(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.SendEmailVerificationCode(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Send a one-time verification code to the given email address. Rate-limited to 1 per 60 seconds.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAuthEmailSendRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Auth.SendEmailVerificationCode(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostAuthEmailSendRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.VerifyEmailCodeAndAuthenticate(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebAuthResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Verify the email code and return JWT tokens. Creates a new user account if this email is not registered.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAuthEmailVerifyRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Auth.VerifyEmailCodeAndAuthenticate(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostAuthEmailVerifyRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.ExchangeGitHubCodeForTokensAPI(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Exchange a GitHub OAuth authorization code for JWT tokens. Use this from SPAs/mobile apps instead of the web redirect flow.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAuthGithubRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Auth.ExchangeGitHubCodeForTokensAPI(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostAuthGithubRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.GitHubOAuthCallbackWeb() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handle the GitHub OAuth redirect, exchange the code for tokens, and redirect to the frontend.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAuthGithubCallbackRequest{
        State: "state",
        Code: "code",
    }
client.Auth.GitHubOAuthCallbackWeb(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**state:** `string` — OAuth state
    
</dd>
</dl>

<dl>
<dd>

**code:** `string` — GitHub authorization code
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.InitiateGitHubOAuth() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Generate an OAuth state and redirect the browser to GitHub's authorization page.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAuthGithubLoginRequest{
        RefURI: "ref_uri",
    }
client.Auth.InitiateGitHubOAuth(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**refURI:** `string` — Post-auth redirect URI (will be redirected to verbatim)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.ExchangeGoogleCodeForTokensAPI(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Exchange a Google OAuth authorization code for JWT tokens. Use this from SPAs/mobile apps instead of the web redirect flow.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAuthGoogleRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Auth.ExchangeGoogleCodeForTokensAPI(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostAuthGoogleRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.GoogleOAuthCallbackWeb() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handle the Google OAuth redirect, exchange the code for tokens, and redirect to the frontend.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAuthGoogleCallbackRequest{
        State: "state",
        Code: "code",
    }
client.Auth.GoogleOAuthCallbackWeb(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**state:** `string` — OAuth state
    
</dd>
</dl>

<dl>
<dd>

**code:** `string` — Google authorization code
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.InitiateGoogleOAuth() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Generate an OAuth state and redirect the browser to Google's authorization page.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetAuthGoogleLoginRequest{
        RefURI: "ref_uri",
    }
client.Auth.InitiateGoogleOAuth(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**refURI:** `string` — Post-auth redirect URI (will be redirected to verbatim)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.LogoutCurrentUser() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Invalidate all sessions for the authenticated user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Auth.LogoutCurrentUser(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.SendSmsVerificationCode(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Send a one-time verification code to the given phone number. Rate-limited to 1 per 60 seconds.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAuthSmsSendRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Auth.SendSmsVerificationCode(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostAuthSmsSendRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Auth.VerifySmsCodeAndAuthenticate(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebAuthResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Verify the SMS code and return JWT tokens. Creates a new user account if this phone is not registered.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostAuthSmsVerifyRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Auth.VerifySmsCodeAndAuthenticate(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostAuthSmsVerifyRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Bulletins
<details><summary><code>client.Bulletins.ListPublishedBulletins() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalBulletinInternalDomainBulletin</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return a paginated list of published bulletins with optional filters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetBulletinsRequest{}
client.Bulletins.ListPublishedBulletins(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**type_:** `*string` — Filter by type
    
</dd>
</dl>

<dl>
<dd>

**category:** `*string` — Filter by category
    
</dd>
</dl>

<dl>
<dd>

**section:** `*string` — Filter by section
    
</dd>
</dl>

<dl>
<dd>

**version:** `*string` — Filter by version
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Max results
    
</dd>
</dl>

<dl>
<dd>

**cursorVal:** `*int` — Cursor value for pagination
    
</dd>
</dl>

<dl>
<dd>

**cursorID:** `*int` — Cursor ID for pagination
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Bulletins.GetBulletinByID(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalBulletinInternalDomainBulletin</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return a single published bulletin by its ID. Returns 404 if not found or expired.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetBulletinsIDRequest{
        ID: 1,
    }
client.Bulletins.GetBulletinByID(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Bulletin ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Chat
<details><summary><code>client.Chat.SendAChatCompletionRequest(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Proxies a chat completion to the upstream LLM provider. Supports streaming (SSE) and non-streaming.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := map[string]any{
        "key": "value",
    }
client.Chat.SendAChatCompletionRequest(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `map[string]any` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Chat.SendAnAnthropicCompatibleMessageRequest(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAnthropicMessageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Adapts Anthropic Messages API requests and responses to the existing AI gateway routing and proxy pipeline.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostMessagesRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Chat.SendAnAnthropicCompatibleMessageRequest(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostMessagesRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Chat.ListAvailableModels() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all enabled models with extended metadata (name, description, capabilities, default flag).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Chat.ListAvailableModels(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Chat.SendAResponsesAPIRequest(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Adapts OpenAI Responses API requests to Chat Completions. Primarily for Codex CLI compatibility.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := map[string]any{
        "key": "value",
    }
client.Chat.SendAResponsesAPIRequest(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `map[string]any` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## WisdomCommunityPublic
<details><summary><code>client.WisdomCommunityPublic.ListPublicCommunities() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List public communities without authentication. When slug is provided, username is required for joint lookup.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetCommunityRequest{}
client.WisdomCommunityPublic.ListPublicCommunities(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**username:** `*string` — username filter, required when slug is provided
    
</dd>
</dl>

<dl>
<dd>

**slug:** `*string` — community slug, requires username
    
</dd>
</dl>

<dl>
<dd>

**offset:** `*int` — pagination offset, default 0
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — pagination limit, default 20, max 100
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## UserGateway
<details><summary><code>client.UserGateway.ListUserModels(UserID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalAigatewayInternalDomainModel</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return models owned by the path user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewayUserIDModelsRequest{
        UserID: 1,
    }
client.UserGateway.ListUserModels(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserGateway.CreateUserModel(UserID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalAigatewayInternalDomainModel</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a user-owned billable model and bind its primary provider.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewayUserIDModelsRequest{
        UserID: 1,
        Body: &mktsdkgo.PostGatewayUserIDModelsRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.UserGateway.CreateUserModel(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostGatewayUserIDModelsRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserGateway.GetVisibleUserModel(UserID, ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalAigatewayInternalDomainModel</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return one model visible to the path user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewayUserIDModelsIDRequest{
        UserID: 1,
        ID: 1,
    }
client.UserGateway.GetVisibleUserModel(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Model ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserGateway.UpdateUserModel(UserID, ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalAigatewayInternalDomainModel</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a user-owned billable domain.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PutGatewayUserIDModelsIDRequest{
        UserID: 1,
        ID: 1,
        Body: &mktsdkgo.PutGatewayUserIDModelsIDRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.UserGateway.UpdateUserModel(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Model ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PutGatewayUserIDModelsIDRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserGateway.DeleteUserModel(UserID, ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a user-owned model and all its grants.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteGatewayUserIDModelsIDRequest{
        UserID: 1,
        ID: 1,
    }
client.UserGateway.DeleteUserModel(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Model ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserGateway.ListAModelToMarketplace(UserID, ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalAigatewayInternalDomainModel</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List a user-owned model to the public marketplace. Requires provider to be enabled, pricing to be set, and a revenue wallet.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewayUserIDModelsIDListRequest{
        UserID: 1,
        ID: 1,
    }
client.UserGateway.ListAModelToMarketplace(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Model ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserGateway.UnlistAModelFromMarketplace(UserID, ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalAigatewayInternalDomainModel</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Unlist a user-owned model from the public marketplace (visibility = private).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewayUserIDModelsIDUnlistRequest{
        UserID: 1,
        ID: 1,
    }
client.UserGateway.UnlistAModelFromMarketplace(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Model ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## UserModels
<details><summary><code>client.UserModels.ListModelAccessGrants(UserID, ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalIamAccessGrant</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return all access grants for a model
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewayUserIDModelsIDGrantsRequest{
        UserID: 1,
        ID: 1,
    }
client.UserModels.ListModelAccessGrants(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Model ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserModels.GrantModelAccess(UserID, ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Grant a user access to a private model
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewayUserIDModelsIDGrantsRequest{
        UserID: 1,
        ID: 1,
        Body: &mktsdkgo.PostGatewayUserIDModelsIDGrantsRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.UserModels.GrantModelAccess(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Model ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostGatewayUserIDModelsIDGrantsRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserModels.RevokeModelAccess(UserID, ID, TargetUserID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Revoke a user's access to a model
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteGatewayUserIDModelsIDGrantsTargetUserIDRequest{
        UserID: 1,
        ID: 1,
        TargetUserID: 1,
    }
client.UserModels.RevokeModelAccess(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Model ID
    
</dd>
</dl>

<dl>
<dd>

**targetUserID:** `int` — Target user ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## UserProviders
<details><summary><code>client.UserProviders.ListVisibleProviders(UserID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayInternalAigatewayInternalWebUserProviderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return user-owned and global providers with masked API keys.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewayUserIDProvidersRequest{
        UserID: 1,
    }
client.UserProviders.ListVisibleProviders(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserProviders.CreateUserProvider(UserID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebUserProviderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a user-owned LLM provider with encrypted API service.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewayUserIDProvidersRequest{
        UserID: 1,
        Body: &mktsdkgo.PostGatewayUserIDProvidersRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.UserProviders.CreateUserProvider(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostGatewayUserIDProvidersRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserProviders.GetVisibleProvider(UserID, ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebUserProviderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return one visible provider with masked API service.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewayUserIDProvidersIDRequest{
        UserID: 1,
        ID: 1,
    }
client.UserProviders.GetVisibleProvider(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Provider ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserProviders.UpdateUserProvider(UserID, ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebUserProviderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a user-owned provider. Global providers cannot be modified.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PutGatewayUserIDProvidersIDRequest{
        UserID: 1,
        ID: 1,
        Body: &mktsdkgo.PutGatewayUserIDProvidersIDRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.UserProviders.UpdateUserProvider(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Provider ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PutGatewayUserIDProvidersIDRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserProviders.DeleteUserProvider(UserID, ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a user-owned provider if no user models reference it.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteGatewayUserIDProvidersIDRequest{
        UserID: 1,
        ID: 1,
    }
client.UserProviders.DeleteUserProvider(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Provider ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserProviders.TestExistingProvider(UserID, ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebTestProviderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Test an existing provider's connectivity and re-discover available models.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewayUserIDProvidersIDTestRequest{
        UserID: 1,
        ID: 1,
    }
client.UserProviders.TestExistingProvider(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Provider ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserProviders.TestProviderConnection(UserID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebTestProviderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Test provider connectivity and list available models, before creating a provider record.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewayUserIDProvidersTestRequest{
        UserID: 1,
        Body: &mktsdkgo.PostGatewayUserIDProvidersTestRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.UserProviders.TestProviderConnection(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostGatewayUserIDProvidersTestRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## UserRoutes
<details><summary><code>client.UserRoutes.ListUserModelRoutes(UserID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayInternalAigatewayInternalWebUserRouteResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return all routes for the authenticated user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewayUserIDRoutesRequest{
        UserID: 1,
    }
client.UserRoutes.ListUserModelRoutes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserRoutes.CreateUserModelRoute(UserID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebUserRouteResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a user-scoped model_prefix → provider routing override.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewayUserIDRoutesRequest{
        UserID: 1,
        Body: &mktsdkgo.PostGatewayUserIDRoutesRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.UserRoutes.CreateUserModelRoute(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostGatewayUserIDRoutesRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserRoutes.GetUserModelRoute(UserID, ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebUserRouteResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return a single route by ID
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewayUserIDRoutesIDRequest{
        UserID: 1,
        ID: 1,
    }
client.UserRoutes.GetUserModelRoute(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Route ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserRoutes.DeleteUserModelRoute(UserID, ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a user route by ID
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteGatewayUserIDRoutesIDRequest{
        UserID: 1,
        ID: 1,
    }
client.UserRoutes.DeleteUserModelRoute(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Route ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserRoutes.ListRouteAccessGrants(UserID, ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalIamAccessGrant</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return all access grants for a route
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewayUserIDRoutesIDGrantsRequest{
        UserID: 1,
        ID: 1,
    }
client.UserRoutes.ListRouteAccessGrants(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Route ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserRoutes.GrantRouteAccess(UserID, ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Grant a user access to a private route
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewayUserIDRoutesIDGrantsRequest{
        UserID: 1,
        ID: 1,
        Body: &mktsdkgo.PostGatewayUserIDRoutesIDGrantsRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.UserRoutes.GrantRouteAccess(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Route ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostGatewayUserIDRoutesIDGrantsRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserRoutes.RevokeRouteAccess(UserID, ID, TargetUserID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Revoke a user's access to a route
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteGatewayUserIDRoutesIDGrantsTargetUserIDRequest{
        UserID: 1,
        ID: 1,
        TargetUserID: 1,
    }
client.UserRoutes.RevokeRouteAccess(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Route ID
    
</dd>
</dl>

<dl>
<dd>

**targetUserID:** `int` — Target user ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Gateway
<details><summary><code>client.Gateway.TestModelConnectivity(UserID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebTestModelResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Sends a "say hi" prompt to the specified provider+model and returns the response.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewayUserIDTestModelRequest{
        UserID: 1,
        Body: &mktsdkgo.PostGatewayUserIDTestModelRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Gateway.TestModelConnectivity(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID or username
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostGatewayUserIDTestModelRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Gateway.ListRequestLogs() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebListLogsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns paginated request logs for the current user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewayLogsRequest{}
client.Gateway.ListRequestLogs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**modelID:** `*int` — Filter by model ID
    
</dd>
</dl>

<dl>
<dd>

**providerID:** `*int` — Filter by provider ID
    
</dd>
</dl>

<dl>
<dd>

**sessionID:** `*int` — Filter by session ID
    
</dd>
</dl>

<dl>
<dd>

**status:** `*int` — Filter by HTTP status code
    
</dd>
</dl>

<dl>
<dd>

**stream:** `*bool` — Filter by stream (true/false)
    
</dd>
</dl>

<dl>
<dd>

**dateFrom:** `*string` — Start date (YYYY-MM-DD)
    
</dd>
</dl>

<dl>
<dd>

**dateTo:** `*string` — End date (YYYY-MM-DD)
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*string` — Sort field: created_at, latency_ms, cost, total_tokens
    
</dd>
</dl>

<dl>
<dd>

**order:** `*string` — Sort order: asc, desc (default desc)
    
</dd>
</dl>

<dl>
<dd>

**offset:** `*int` — Pagination offset (default 0)
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Page size (default 20, max 100)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Gateway.ListModelsVisibleToCurrentPrincipal() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns models that the current authenticated user (via cookie or API key) is allowed to see.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Gateway.ListModelsVisibleToCurrentPrincipal(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Gateway.SellerRevenueSummary() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebSellerRevenueResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns revenue summary for all models owned by the current user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewaySellerRevenueRequest{}
client.Gateway.SellerRevenueSummary(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**period:** `*string` — Period: today, week, all (default all)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Gateway.ListUsageRecords() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebListUsageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns paginated daily usage records for the current user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewayUsageRequest{}
client.Gateway.ListUsageRecords(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**modelID:** `*int` — Filter by model ID
    
</dd>
</dl>

<dl>
<dd>

**dateFrom:** `*string` — Start date (YYYY-MM-DD)
    
</dd>
</dl>

<dl>
<dd>

**dateTo:** `*string` — End date (YYYY-MM-DD)
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*string` — Sort field: record_date, call_count, total_cost
    
</dd>
</dl>

<dl>
<dd>

**order:** `*string` — Sort order: asc, desc (default desc)
    
</dd>
</dl>

<dl>
<dd>

**offset:** `*int` — Pagination offset (default 0)
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Page size (default 20, max 100)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Sessions
<details><summary><code>client.Sessions.ListAiSessions() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalAigatewayInternalDomainAiSession</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return paginated list of AI chat sessions for the current user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetGatewaySessionsRequest{}
client.Sessions.ListAiSessions(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**cursor:** `*string` — Pagination cursor
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Page size (default 20, max 100)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sessions.CreateAiSession(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalAigatewayInternalDomainAiSession</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new AI chat session for the current user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostGatewaySessionsRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Sessions.CreateAiSession(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostGatewaySessionsRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sessions.DeleteAiSession(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Soft-delete an AI chat session
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteGatewaySessionsIDRequest{
        ID: 1,
    }
client.Sessions.DeleteAiSession(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Session ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sessions.UpdateAiSession(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultAny</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update session title or metadata
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PatchGatewaySessionsIDRequest{
        ID: 1,
        Body: &mktsdkgo.PatchGatewaySessionsIDRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Sessions.UpdateAiSession(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Session ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PatchGatewaySessionsIDRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Iam
<details><summary><code>client.Iam.ListAPIKeys() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayInternalIamInternalWebAPIKeyResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List API key metadata for the authenticated user. Raw keys and hashes are never returned.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Iam.ListAPIKeys(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Iam.CreateAPIKey(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalIamInternalWebCreateAPIKeyResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create an API key for the authenticated user. The raw API key is returned only once in this response.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostIamAPIKeysRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Iam.CreateAPIKey(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostIamAPIKeysRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Iam.RevokeAPIKey(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Revoke an API key owned by the authenticated user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteIamAPIKeysIDRequest{
        ID: 1,
    }
client.Iam.RevokeAPIKey(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — API key ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Iam.ListResourceAccessGrants() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalIamInternalDomainAccessGrant</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

列出资源的所有访问授权记录。
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetIamGrantsRequest{
        ResourceType: "resource_type",
        ResourceID: 1,
    }
client.Iam.ListResourceAccessGrants(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**resourceType:** `string` — Resource type
    
</dd>
</dl>

<dl>
<dd>

**resourceID:** `int` — Resource ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Iam.GrantResourceAccess(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

授予用户资源访问权限。将指定用户加入资源的授权白名单。
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostIamGrantsRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Iam.GrantResourceAccess(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostIamGrantsRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Iam.RevokeResourceAccess(ResourceType, ResourceID, UserID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

撤销用户的资源访问权限，将指定用户从资源的授权白名单中移除。
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteIamGrantsResourceTypeResourceIDUserIDRequest{
        ResourceType: "resource_type",
        ResourceID: 1,
        UserID: 1,
    }
client.Iam.RevokeResourceAccess(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**resourceType:** `string` — Resource type
    
</dd>
</dl>

<dl>
<dd>

**resourceID:** `int` — Resource ID
    
</dd>
</dl>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Marketplace
<details><summary><code>client.Marketplace.ListMarketplaceModels() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAigatewayInternalWebMarketplaceListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns paginated marketplace models with search, price filter, and sort.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetMarketplaceModelsRequest{}
client.Marketplace.ListMarketplaceModels(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**search:** `*string` — Search by name or description
    
</dd>
</dl>

<dl>
<dd>

**minPrice:** `*float64` — Minimum output price filter
    
</dd>
</dl>

<dl>
<dd>

**maxPrice:** `*float64` — Maximum output price filter
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*string` — Sort field: listed_at, call_count, output_price (default listed_at)
    
</dd>
</dl>

<dl>
<dd>

**order:** `*string` — Sort order: asc, desc (default desc)
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number (default 1)
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Page size (default 20, max 100)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Conversations
<details><summary><code>client.Conversations.ListConversations() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalMessagingInternalDomainConversationSummary</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List conversations for the current user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Conversations.ListConversations(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Conversations.CreateConversation(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalMessagingInternalDomainConversation</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new conversation with participants
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostMessagingConversationsRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Conversations.CreateConversation(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostMessagingConversationsRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Conversations.GetConversation(ConvID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalMessagingInternalDomainConversation</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a conversation by ID
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetMessagingConversationsConvIDRequest{
        ConvID: 1,
    }
client.Conversations.GetConversation(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**convID:** `int` — Conversation ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Conversations.AddParticipant(ConvID, request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add a user to a conversation
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostMessagingConversationsConvIDParticipantsRequest{
        ConvID: 1,
        Body: &mktsdkgo.PostMessagingConversationsConvIDParticipantsRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Conversations.AddParticipant(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**convID:** `int` — Conversation ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostMessagingConversationsConvIDParticipantsRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Messages
<details><summary><code>client.Messages.GetMessages(ConvID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayGithubComMktAgiAixInternalMessagingInternalDomainMessage</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve messages in a conversation
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetMessagingConversationsConvIDMessagesRequest{
        ConvID: 1,
    }
client.Messages.GetMessages(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**convID:** `int` — Conversation ID
    
</dd>
</dl>

<dl>
<dd>

**afterSeq:** `*int` — Only messages after this sequence number
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Page limit (default 20, max 100)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Messages.SendMessage(ConvID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultGithubComMktAgiAixInternalMessagingInternalDomainMessage</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Send a message in a conversation
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostMessagingConversationsConvIDMessagesRequest{
        ConvID: 1,
        Body: &mktsdkgo.PostMessagingConversationsConvIDMessagesRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Messages.SendMessage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**convID:** `int` — Conversation ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostMessagingConversationsConvIDMessagesRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Messages.MarkMessagesAsRead(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Mark messages as read up to the given sequence number
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostMessagingReadRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Messages.MarkMessagesAsRead(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostMessagingReadRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Devices
<details><summary><code>client.Devices.RegisterDevice(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Register a push notification device for the current user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostMessagingDevicesRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Devices.RegisterDevice(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostMessagingDevicesRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Devices.UnregisterDevice(DeviceID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Unregister a push notification device
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteMessagingDevicesDeviceIDRequest{
        DeviceID: 1,
    }
client.Devices.UnregisterDevice(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**deviceID:** `int` — Device ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## WisdomPublic
<details><summary><code>client.WisdomPublic.ListPublicContents() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List public content nodes without authentication
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetPublicWisdomRequest{}
client.WisdomPublic.ListPublicContents(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**username:** `*string` — filter by author username (resolved to user_id by middleware)
    
</dd>
</dl>

<dl>
<dd>

**kind:** `*string` — kind filter
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*string` — type filter
    
</dd>
</dl>

<dl>
<dd>

**communityID:** `*int` — community ID filter
    
</dd>
</dl>

<dl>
<dd>

**communitySlug:** `*string` — community slug filter, requires username
    
</dd>
</dl>

<dl>
<dd>

**slug:** `*string` — slug filter, scoped within community_slug when present
    
</dd>
</dl>

<dl>
<dd>

**promiseSearch:** `*string` — search by promise keyword
    
</dd>
</dl>

<dl>
<dd>

**offset:** `*int` — pagination offset, default 0
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — pagination limit, default 20, max 100
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## UserSecrets
<details><summary><code>client.UserSecrets.ListUserSecrets(UserID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayInternalAccountsInternalWebUserSecretResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List metadata for all secrets owned by the specified user. Secret values are never returned by this endpoint.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetSecretsUserIDRequest{
        UserID: 1,
    }
client.UserSecrets.ListUserSecrets(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserSecrets.GetUserSecret(UserID, Key) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebUserSecretValueResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return one decrypted secret value for the specified user and service.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetSecretsUserIDKeyRequest{
        UserID: 1,
        Key: "key",
    }
client.UserSecrets.GetUserSecret(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**key:** `string` — Secret key
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserSecrets.CreateOrUpdateUserSecret(UserID, Key, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebUserSecretResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Encrypt and store a secret value for the specified user and service. The response does not include the secret value.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PutSecretsUserIDKeyRequest{
        UserID: 1,
        Key: "key",
        Body: &mktsdkgo.PutSecretsUserIDKeyRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.UserSecrets.CreateOrUpdateUserSecret(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**key:** `string` — Secret key
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PutSecretsUserIDKeyRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.UserSecrets.DeleteUserSecret(UserID, Key) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebDeleteUserSecretResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete one secret by user ID and service.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteSecretsUserIDKeyRequest{
        UserID: 1,
        Key: "key",
    }
client.UserSecrets.DeleteUserSecret(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userID:** `int` — User ID
    
</dd>
</dl>

<dl>
<dd>

**key:** `string` — Secret key
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## User
<details><summary><code>client.User.GetCurrentUserProfile() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebUserResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return the authenticated user's profile information.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.User.GetCurrentUserProfile(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.UpdateCurrentUserProfile(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebUserResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update the authenticated user's name and/or avatar_url. Name must be unique.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PatchUserMeRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.User.UpdateCurrentUserProfile(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PatchUserMeRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.GetPresignedAvatarUploadURL(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebAvatarUploadURLResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Generate a presigned S3 URL for direct browser avatar upload. Content type must be image/png, image/jpeg, or image/webp. Max size 5MB.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostUserMeAvatarUploadURLRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.User.GetPresignedAvatarUploadURL(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostUserMeAvatarUploadURLRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.ConfirmAndSoftDeleteTheAccount(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Verify the deletion code, snapshot original contacts, NULL the login identifiers, kill all sessions, and clear the session cookie.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostUserMeDeletionConfirmRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.User.ConfirmAndSoftDeleteTheAccount(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostUserMeDeletionConfirmRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.SendAccountDeletionConfirmationCode(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Send a 6-digit confirmation code to the user's bound email (or phone if no email) to confirm account deletion.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := map[string]any{
        "key": "value",
    }
client.User.SendAccountDeletionConfirmationCode(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `map[string]any` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.SwitchCurrentSessionUser(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalAccountsInternalWebUserResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Switch the session's current effective user to the session owner or one direct sub-user of the owner.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostUserSwitchRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.User.SwitchCurrentSessionUser(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostUserSwitchRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.ListSwitchableUsers() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayInternalAccountsInternalWebUserResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return the session owner plus all direct sub-users that the current session can switch to.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.User.ListSwitchableUsers(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Accounts
<details><summary><code>client.Accounts.ReceiveGitHubWebhookEvents(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handle incoming GitHub webhook events (installation, push, etc.)
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := map[string]any{
        "key": "value",
    }
client.Accounts.ReceiveGitHubWebhookEvents(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `map[string]any` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Wisdom
<details><summary><code>client.Wisdom.ListContents() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List content nodes with optional filters (kind, type, community_id, etc.)
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetWisdomRequest{}
client.Wisdom.ListContents(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**kind:** `*string` — kind filter
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*string` — type filter
    
</dd>
</dl>

<dl>
<dd>

**communityID:** `*int` — community ID filter
    
</dd>
</dl>

<dl>
<dd>

**minConfidence:** `*float64` — minimum confidence filter
    
</dd>
</dl>

<dl>
<dd>

**promiseSearch:** `*string` — search by promise keyword
    
</dd>
</dl>

<dl>
<dd>

**offset:** `*int` — pagination offset, default 0
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — pagination limit, default 20, max 100
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wisdom.CreateContent(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebWisdomResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new content node in the property graph
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostWisdomRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.Wisdom.CreateContent(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostWisdomRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wisdom.GetContent(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebWisdomWithContextResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get a content node by ID with optional depth context (0 or 1)
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetWisdomIDRequest{
        ID: 1,
    }
client.Wisdom.GetContent(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Content ID
    
</dd>
</dl>

<dl>
<dd>

**depth:** `*int` — Context depth: 0 (default) or 1
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wisdom.DeleteContent(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebWisdomDeleteVo</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a content node by ID
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteWisdomIDRequest{
        ID: 1,
    }
client.Wisdom.DeleteContent(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Content ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wisdom.UpdateContent(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebWisdomResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a content node's fields with optimistic locking via version
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PatchWisdomIDRequest{
        ID: 1,
        Body: &mktsdkgo.PatchWisdomIDRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Wisdom.UpdateContent(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Content ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PatchWisdomIDRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wisdom.GetContentLogs(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayInternalWisdomInternalWebLogResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get audit log entries for a specific content node
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetWisdomIDLogsRequest{
        ID: 1,
    }
client.Wisdom.GetContentLogs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Content ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wisdom.AddRelation(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebRelationResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add a directed relation edge from source content to target content
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostWisdomIDRelationsRequest{
        ID: 1,
        Body: &mktsdkgo.PostWisdomIDRelationsRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.Wisdom.AddRelation(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Source content ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PostWisdomIDRelationsRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wisdom.RemoveRelation(ID, Rid) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebWisdomDeleteVo</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Remove a relation edge by relation ID
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteWisdomIDRelationsRidRequest{
        ID: 1,
        Rid: 1,
    }
client.Wisdom.RemoveRelation(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Source content ID
    
</dd>
</dl>

<dl>
<dd>

**rid:** `int` — Relation ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wisdom.ClusterContents() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebTriggerStatusVo</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Trigger community detection clustering on user's content graph
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wisdom.ClusterContents(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wisdom.ListPurchasedCommunities() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultArrayInternalWisdomInternalWebPurchaseItemResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List the current user's purchased community access grants
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wisdom.ListPurchasedCommunities(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wisdom.GetSubgraph() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebGraphResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the content subgraph for a specific community
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetWisdomSubgraphRequest{
        CommunityID: 1,
    }
client.Wisdom.GetSubgraph(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**communityID:** `int` — Community ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## WisdomCommunity
<details><summary><code>client.WisdomCommunity.ListCommunities() -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List communities for the current user with pagination
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetWisdomCommunityRequest{}
client.WisdomCommunity.ListCommunities(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**offset:** `*int` — pagination offset, default 0
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — pagination limit, default 20, max 100
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.WisdomCommunity.CreateCommunity(request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebCommunityResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new community
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostWisdomCommunityRequest{
        StringUnknownMap: map[string]any{
            "key": "value",
        },
    }
client.WisdomCommunity.CreateCommunity(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*mktsdkgo.PostWisdomCommunityRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.WisdomCommunity.GetCommunity(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebCommunityResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get a community by ID
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetWisdomCommunityIDRequest{
        ID: 1,
    }
client.WisdomCommunity.GetCommunity(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Community ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.WisdomCommunity.DeleteCommunity(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebWisdomDeleteVo</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a community and disassociate its wisdoms
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.DeleteWisdomCommunityIDRequest{
        ID: 1,
    }
client.WisdomCommunity.DeleteCommunity(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Community ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.WisdomCommunity.UpdateCommunity(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebCommunityResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a community's fields
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PatchWisdomCommunityIDRequest{
        ID: 1,
        Body: &mktsdkgo.PatchWisdomCommunityIDRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.WisdomCommunity.UpdateCommunity(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Community ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PatchWisdomCommunityIDRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.WisdomCommunity.SetCommunityPricing(ID, request) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebCommunityResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Set the price, pricing model, and listing status for a community
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PutWisdomCommunityIDPricingRequest{
        ID: 1,
        Body: &mktsdkgo.PutWisdomCommunityIDPricingRequestBody{
            StringUnknownMap: map[string]any{
                "key": "value",
            },
        },
    }
client.WisdomCommunity.SetCommunityPricing(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Community ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*mktsdkgo.PutWisdomCommunityIDPricingRequestBody` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.WisdomCommunity.PurchaseCommunity(ID) -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultMapStringString</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Purchase access to a paid community
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.PostWisdomCommunityIDPurchaseRequest{
        ID: 1,
    }
client.WisdomCommunity.PurchaseCommunity(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Community ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## WisdomMarketplace
<details><summary><code>client.WisdomMarketplace.ListMarketplaceCommunities() -> *mktsdkgo.GithubComMktAgiAixInternalPkgGinxResultInternalWisdomInternalWebMarketplaceListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List published communities in the marketplace with optional filters
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &mktsdkgo.GetWisdomMarketplaceRequest{}
client.WisdomMarketplace.ListMarketplaceCommunities(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**search:** `*string` — Search by label
    
</dd>
</dl>

<dl>
<dd>

**minPrice:** `*float64` — Minimum price filter
    
</dd>
</dl>

<dl>
<dd>

**maxPrice:** `*float64` — Maximum price filter
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*string` — Sort field: created_at, price, member_count
    
</dd>
</dl>

<dl>
<dd>

**order:** `*string` — Sort order: asc, desc
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, default 1
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` — Page limit, default 20, max 100
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

