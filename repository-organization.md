# Repository organization

The content published to docs.microsoft.com is partitioned into several public GitHub repositories. The table below enumerates the current set of docs.microsoft.com landing pages, the GitHub repository that contains the associated articles, and the related discussion forum(s):

| Main Landing Page | Solution/Service Landing Page | GitHub Org/Repository | Discussion Forum(s) |
|:---------------------------:|:-------------------------------------------:|:-------------------------:|:----------------------------:|
| [Enterprise Mobility][EM-Land-Page] |     | [Microsoft/EMDocs][EM-Land-Repo] | [TechNet][Forum-MSDN-EM] |
|     | [Azure Active Directory][EM-AzureAD-Land] | [Azure/Azure-Content][EM-AzureAD-Repo] | [MSDN][Forum-MSDN-AzureAD], [Stack Overflow][Forum-SO-AzureAD] |
|     | [Multi-Factor Authentication][EM-MFA-Land] | [Azure/Azure-Content][EM-MFA-Repo] | [MSDN][Forum-MSDN-MFA], [Stack Overflow][Forum-SO-MFA] |
|     | [Microsoft Identity Manager][EM-MIM-Land] | [Microsoft/MIMDocs][EM-MIM-Repo] | [TechNet][Forum-MSDN-MIM], [Stack Overflow][Forum-SO-MIM] |
|     | [Microsoft Intune][EM-Intune-Land] | [Microsoft/IntuneDocs][EM-Intune-Repo] | [TechNet][Forum-MSDN-Intune], [Stack Overflow][Forum-SO-Intune] |
|     | [Azure Rights Management][EM-AzureRMS-Land] | [Microsoft/Azure-RMSDocs][EM-AzureRMS-Repo] | [Yammer][Forum-Yammer-AzureRMS], [TechNet][Forum-MSDN-AzureRMS], [Stack Overflow][Forum-SO-AzureRMS] |
|     | [Microsoft Advanced Threat Analytics][EM-ATA-Land] | [Microsoft/ATADocs][EM-ATA-Repo] | [TechNet][Forum-MSDN-ATA] |
|     | [Azure RemoteApp][EM-RemoteApp-Land] | [Azure/Azure-Content][EM-RemoteApp-Repo] | [TechNet][Forum-MSDN-RemoteApp], [Stack Overflow][Forum-SO-RemoteApp] |
| [.NET][Dotnet-Page] |     |     | [Stack Overflow][Forum-SO-Dotnet] |
|     | [.NET Core][Dotnet-Core-Page] | [dotnet/core-docs][Dotnet-Core-Repo] | [Stack Overflow][Forum-SO-Dotnet-Core] |

The content in each repository is loosely aligned with the organization of the articles on the corresponding [https://docs.microsoft.com/](https://docs.microsoft.com/) landing pages. A series of subdirectories are used for separation of usage scenarios/stages (that is, Understand & Explore, Deploy & Use, etc.), along with media content (that is, image files) and include files (Markdown files that are reused across multiple main articles).

#### Main articles directory

The main articles directory is found directly off the root of the repository, and contains a set of subdirectories with articles formatted as Markdown files which use an *.md* extension. For example, the main articles directory for the [https://github.com/microsoft/IntuneDocs](https://github.com/microsoft/IntuneDocs) repository is the `/IntuneDocs` subdirectory. 

Within the root of this directory are general articles that relate to the overall service, along with another series of subdirectories, which match the common scenarios as outlined on the main landing page for the service. For instance, the Intune "Understand & Explore" articles are in the `/Understand` subdirectory, "Deploy & Use" articles are found in the `/DeployUse` subdirectory, etc.  

* **Article file names:** Note that file names use the following rules:
    * Contain only lowercase letters, numbers, and hyphens. Windows operating systems are case insensitive, so if you need to rename a file's casing from upper/mixed to lower, you can use the following Git command (use the proper casing as well for both file names):

            git mv <main-directory/scenario-directory/current-file-name.md> <main-directory/scenario-directory/new-file-name.md>
    * No spaces or punctuation characters. Use the hyphens to separate words and numbers in the file name.
    * No more than 80 characters - this is a publishing system limit
    * Use action verbs that are specific, such as develop, buy, build, troubleshoot. No -ing words.
    * No small words - don't include a, and, the, in, or, etc.
    * Must be in Markdown and use the .md file extension.
* **Media subdirectory:** As mentioned, each article directory also contains a `\media` subdirectory for corresponding media files, inside which are images used by articles that have image references.  
* **Includes subdirectory:** Whenever we have reusable content that is shared across two or more articles, it is placed in an `includes` subdirectory off of the main articles directory. In the Markdown file that wishes to use the include file, a corresponding INCLUDE Markdown extension is placed in the location where the include file needs to be referenced.  

     The format of the extension is as follows:

    `> [!INCLUDE[accessibility6](./includes/accessibility6_md.md)]`

    The statement must begin with `> [!INCLUDE`, followed immediately by a user-defined name for the include site enclosed in brackets, `[accessibility6]`, followed immediately by the relative path to the include file enclosed in parentheses, `(./includes/accessibility6_md.md)`, and terminated with the closing bracket, `]`.

#### Markdown file template

For convenience, the root directory of each repository contains a Markdown template file named `template.md`, which you can use as a "starter file" if you need to create a new article for submission to the repository. The file contains:

- A **metadata header** at the top of the file, delineated by two, 3-hyphen lines, and containing the various tags used for tracking information relating to the article. Article metadata enables certain functionality, such as author attribution, contributor attribution, breadcrumbs, article descriptions, and SEO optimizations as well as reporting processes used by Microsoft to evaluate the performance of the content. So the metadata is important!
- A **"Metadata" section** that describes the various metadata tags and values. If you're unsure of the values to use for the metadata section, you can leave them blank, or comment them with a leading hashtag (#) and they will be reviewed/completed by the pull request reviewer for the repository.
- Various **examples of using Markdown** to format the elements of an article.
- General **instructions on the use of Markdown extensions**, which can be used for various types of alerts.
- Examples of **embedding video** using an iframe.
- General **instructions on the use of docs.microsoft.com extensions**, which can be used for special controls such as buttons and selectors.

## Next steps

- [User account setup](./user-account-setup.md)
- Back to [contributors guide](./readme.md)


<!---- Reference links for Docs landing pages, associated GitHub repositories, and related Forums matrix. ------------------>
<!---- PLEASE INSERT URLS IN ASCENDING SORT ORDER, AND REMOVE LOCALE SEGMENT FROM URLS (that is, en-us) FOR LOCALIZED FORUMS! -->
[Dotnet-Page]: https://docs.microsoft.com/dotnet
[Dotnet-Core-Page]: https://docs.microsoft.com/dotnet/articles/welcome
[Dotnet-Core-Repo]: https://github.com/dotnet/core-docs
[EM-ATA-Land]: https://docs.microsoft.com/advanced-threat-analytics/
[EM-ATA-Repo]: https://github.com/Microsoft/ATADocs
[EM-AzureAD-Land]: https://docs.microsoft.com/active-directory/
[EM-AzureAD-Repo]: https://github.com/Azure/azure-content/tree/master/articles/active-directory/
[EM-AzureRMS-Land]: https://docs.microsoft.com/rights-management/
[EM-AzureRMS-Repo]: https://github.com/Microsoft/Azure-RMSDocs
[EM-Intune-Land]: https://docs.microsoft.com/intune/
[EM-Intune-Repo]: https://github.com/microsoft/intuneDocs
[EM-Land-Page]: https://docs.microsoft.com/enterprise-mobility/
[EM-Land-Repo]: https://github.com/Microsoft/EMDocs/
[EM-MFA-Land]: https://docs.microsoft.com/multi-factor-authentication/
[EM-MFA-Repo]: https://github.com/Azure/azure-content/tree/master/articles/multi-factor-authentication
[EM-MIM-Land]: https://docs.microsoft.com/microsoft-identity-manager/
[EM-MIM-Repo]: https://github.com/Microsoft/MIMDocs
[EM-RemoteApp-Land]: https://docs.microsoft.com/en-us/remoteapp/
[EM-RemoteApp-Repo]: https://github.com/Azure/azure-content/tree/master/articles/remoteapp

[Forum-MSDN-ATA]: https://social.technet.microsoft.com/Forums/en-US/home?forum=mata
[Forum-MSDN-AzureAD]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=WindowsAzureAD
[Forum-MSDN-AzureRMS]: https://social.technet.microsoft.com/Forums/en-US/home?forum=rmsapps%2Crmscloud&filter=alltypes&sort=lastpostdesc
[Forum-MSDN-EM]: https://social.technet.microsoft.com/Forums/en-US/home?sort=relevancedesc&brandIgnore=True&searchTerm=Enterprise+Mobility
[Forum-MSDN-Intune]: https://social.technet.microsoft.com/Forums/en-us/home?category=microsoftintune
[Forum-MSDN-Main]: https://social.msdn.microsoft.com/Forums/home
[Forum-MSDN-MFA]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=windowsazureactiveauthentication
[Forum-MSDN-MIM]: https://social.technet.microsoft.com/Forums/en-US/home?category=identitymanagement
[Forum-MSDN-RemoteApp]: https://social.technet.microsoft.com/Forums/en-US/home?filter=alltypes&brandIgnore=True&sort=relevancedesc&searchTerm=Azure+Remote+or+RemoteApp
[Forum-SO-AzureAD]: http://stackoverflow.com/questions/tagged/azure-active-directory
[Forum-SO-AzureRMS]: http://stackoverflow.com/questions/tagged/rights-management
[Forum-SO-Dotnet]: http://stackoverflow.com/questions/tagged/.net
[Forum-SO-Dotnet-Core]: http://stackoverflow.com/questions/tagged/.net-core
[Forum-SO-Main]: http://stackoverflow.com/tags
[Forum-SO-Intune]: http://stackoverflow.com/questions/tagged/intune
[Forum-SO-MFA]: http://stackoverflow.com/search?q=%5Bazure%5D+multi-factor
[Forum-SO-MIM]: http://stackoverflow.com/search?q=Microsoft+Identity+Manager
[Forum-SO-RemoteApp]: http://stackoverflow.com/questions/tagged/remoteapp
[Forum-TechNet-Main]: https://social.technet.microsoft.com/Forums/home
[Forum-Yammer-AzureRMS]: https://www.yammer.com/AskIPTeam
[Forum-Yammer-Main]: https://www.yammer.com/