# Whale [Concrete5](https://www.concrete5.org) Cheat Sheet V8+

This is a collection of Concrete5 cheat sheets, based on the C5 V8+ source code. 

**Contributions are welcome via [issues](https://github.com/shahroq/whale_c5_cheat_sheet/issues) and [pull requests](https://github.com/shahroq/whale_c5_cheat_sheet/pulls).**

## Table of Contents <!-- omit in toc -->
- [Pages (Collections)](#pages-collections)
  - [A page](#a-page)
    - [Get Current page](#get-current-page)
    - [Get a page by a unique identifier](#get-a-page-by-a-unique-identifier)
    - [Get a page data](#get-a-page-data)
    - [Get a page type/template](#get-a-page-typetemplate)
    - [Get a page attribute](#get-a-page-attribute)
    - [Get list of attributes of a page](#get-list-of-attributes-of-a-page)
  - [List of pages](#list-of-pages)
    - [Get list of pages](#get-list-of-pages)
    - [Get list of pages with pagination](#get-list-of-pages-with-pagination)
    - [Filter a page list](#filter-a-page-list)
    - [Sort a page list](#sort-a-page-list)
  - [Page operations](#page-operations)
    - [Add a page](#add-a-page)
    - [Update a page](#update-a-page)
    - [Delete a page](#delete-a-page)
    - [Move a page](#move-a-page)
    - [Copy a Page](#copy-a-page)
    - [Add an extra location URL](#add-an-extra-location-url)
    - [Set/Update an attribute of a page](#setupdate-an-attribute-of-a-page)
    - [Clear an attribute of a page](#clear-an-attribute-of-a-page)
    - [Refresh page cache](#refresh-page-cache)
- [Files](#files)
  - [A Files](#a-files)
    - [Get a file by a unique identifier](#get-a-file-by-a-unique-identifier)
    - [Get a file data](#get-a-file-data)
    - [Get a file attribute](#get-a-file-attribute)
    - [Get list of attributes of a file](#get-list-of-attributes-of-a-file)
  - [List of files](#list-of-files)
    - [Get list of files](#get-list-of-files)
    - [Get list of files with pagination](#get-list-of-files-with-pagination)
    - [Filter a file list](#filter-a-file-list)
    - [Get files inside a folder](#get-files-inside-a-folder)
    - [Sort a file list](#sort-a-file-list)
    - [Get a file set](#get-a-file-set)
    - [Get a file folder](#get-a-file-folder)
  - [File Operation](#file-operation)
    - [Importing a file](#importing-a-file)
    - [Delete a file](#delete-a-file)
    - [Set/Update an attribute to a file](#setupdate-an-attribute-to-a-file)
    - [Clear an attribute of a file](#clear-an-attribute-of-a-file)
    - [Create a file set](#create-a-file-set)
    - [Add a file to a set](#add-a-file-to-a-set)
    - [Create a file folder](#create-a-file-folder)
    - [Add a file to a folder](#add-a-file-to-a-folder)
- [Users](#users)
  - [A User](#a-user)
    - [Get/Check current user](#getcheck-current-user)
    - [Get a user by a unique identifier](#get-a-user-by-a-unique-identifier)
    - [Get a user data](#get-a-user-data)
    - [Get user info object](#get-user-info-object)
    - [Get user info data](#get-user-info-data)
    - [Get a user (info) attributes](#get-a-user-info-attributes)
  - [List of users](#list-of-users)
    - [Get list of users](#get-list-of-users)
    - [Get list of users with pagination](#get-list-of-users-with-pagination)
    - [Filter a user list](#filter-a-user-list)
    - [Sort a user list](#sort-a-user-list)
  - [User operation](#user-operation)
    - [Add a user](#add-a-user)
    - [Update a user](#update-a-user)
    - [Activate/Deactivate a user](#activatedeactivate-a-user)
    - [Delete a user](#delete-a-user)
    - [Set/Update an attribute to a user](#setupdate-an-attribute-to-a-user)
    - [Clear an attribute of a user](#clear-an-attribute-of-a-user)
- [Attributes](#attributes)
  - [Attribute operations](#attribute-operations)
    - [Add an attribute](#add-an-attribute)
    - [Delete an attribute](#delete-an-attribute)
    - [List of attribute set categories (collection/user/file/site/event)](#list-of-attribute-set-categories-collectionuserfilesiteevent)
    - [List of sets in a category](#list-of-sets-in-a-category)
    - [Get a Collection/Page attribute](#get-a-collectionpage-attribute)
    - [Get options of an 'Option List' attribute](#get-options-of-an-option-list-attribute)
  - [Attrubute Set](#attrubute-set)
    - [A set](#a-set)
    - [Attributes in a set](#attributes-in-a-set)
    - [Add a Collection/Page set](#add-a-collectionpage-set)
    - [Add a File set](#add-a-file-set)
    - [List of sets](#list-of-sets)
- [Themes](#themes)
  - [Page types](#page-types)
    - [Adding areas in a Page Template](#adding-areas-in-a-page-template)
    - [Embedding Blocks in a Page Template](#embedding-blocks-in-a-page-template)
- [Single Pages](#single-pages)
- [Blocks](#blocks)
- [Stacks](#stacks)
- [Packages](#packages)
- [Express Entries](#express-entries)
- [Language](#language)
- [Constants](#constants)
- [Configs](#configs)
- [Helpers](#helpers)
    - [General](#general)
    - [Number helper](#number-helper)
    - [Text helper](#text-helper)
    - [URL helper](#url-helper)
    - [Array helper](#array-helper)
    - [Arrays validation helper](#arrays-validation-helper)
    - [Numbers validation helper](#numbers-validation-helper)
    - [Strings validation helper](#strings-validation-helper)
    - [JSON helper](#json-helper)
    - [Ajax helper](#ajax-helper)
    - [HTML helper](#html-helper)
    - [Date helper](#date-helper)
    - [Image helper](#image-helper)
- [System Operations](#system-operations)
  - [Database](#database)
    - [Current database](#current-database)
    - [Another database](#another-database)
  - [Misc.](#misc)
    - [URL](#url)
    - [Logging](#logging)
    - [Get environment](#get-environment)
    - [Clear site cache](#clear-site-cache)
- [Contributors](#contributors)



## Pages (Collections)



### A page


#### Get Current page
```PHP
$page = \Page::getCurrentPage();
```

#### Get a page by a unique identifier
```PHP
$page = \Page::getByID(1); //by ID
$page = \Page::getByPath('/path/to/page'); //by path
```

#### Get a page data
```PHP
echo $page->getCollectionID();
echo $page->getCollectionName();
echo $page->getCollectionDescription();
echo $page->getCollectionDateAdded();
echo $page->getCollectionDatePublic();
echo $page->getCollectionUserID();
echo $page->getCollectionPath();
echo $page->getCollectionLink();
echo $page->getCollectionParentID();
echo $page->isSystemPage();
```

#### Get a page type/template
```PHP
//Page Template
$pt = $page->getPageTemplateObject();
if (is_object($pt)) {
    $ptID = $pt->getPageTemplateID(); //echo $ptID;
    $ptName = $pt->getPageTemplateName(); //echo $ptName;
    $ptHandle = $pt->getPageTemplateHandle(); //echo $ptHandle;
}        

//Page Type (not working)
$pt = $page->getPageTypeObject();
if (is_object($pt)) {
    $ptID = $pt->getPageTypeID(); //echo $ptID;
    $ptName = $pt->getPageTypeName(); //echo $ptName;
    $ptHandle = $pt->getPageTypeHandle(); //echo $ptHandle;
}        
```

#### Get a page attribute
```PHP
//attribute
$attr = $page->getAttribute('attribute_handle');

//Option List: get options
foreach ((object)$attr as $option) {
    $optionID = $option->getSelectAttributeOptionID(); //echo $optionID;
    $optionValue = $option->getSelectAttributeOptionValue(); //echo $optionValue;
}

//Image/File
if ($attr) {
    $attrURL = $attr->getURL(); //echo $attrURL);
    $attrDownloadURL = $attr->getDownloadURL(); //echo $attrDownloadURL;
    $attrForceDownloadURL = $attr->getForceDownloadURL(); //echo $attrForceDownloadURL;
    $attrSize = $attr->getSize(); //echo $attrSize;
    $attrExtension = $attr->getExtension(); //echo $attrExtension;

    //image thumbnail
    $im = Core::make('helper/image');
    $thumbSrc = $im->getThumbnail($attr, 100, 100)->src; //echo $thumbSrc;
}
```

#### Get list of attributes of a page
```PHP

```

### List of pages


#### Get list of pages
```PHP
$pageList = new PageList();

$pages = $pageList->getResults();

//echo count($pages);
foreach ((array)$pages as $page) {
    echo $page->getCollectionID();
}
```

#### Get list of pages with pagination
```PHP
$pageList = new PageList();

$pagination = $pageList->getPagination();
$pagination->setMaxPerPage(10);
$pagination->setCurrentPage(1);
$pages = $pagination->getCurrentPageResults();

//Pagination functions
echo $pagination->getTotalResults(); //total number of results
echo $pagination->getTotalPages(); //total number of pages
echo $pagination->hasNextPage(); //To determine whether paging is necessary
echo $pagination->hasPreviousPage(); //"
echo $pagination->renderDefaultView(); //Outputs HTML for Bootstrap 3. 

//echo count($pages);
foreach ((array)$pages as $page) {
    echo $page->getCollectionID();
}
```
For custom markup check [`here`](https://documentation.concrete5.org/tutorials/styling-the-pagination-5-7)

#### Filter a page list
```PHP
$pageList->filterByParentID($cParentID); //by parent ID

$pageList->filterByKeywords('foobar'); //by keyword
$pageList->filterByFulltextKeywords('foobar'); //more advanced search by keyword

$pageList->filterByPageTypeID($ctID); //by a page type ID
$pageList->filterByPageTypeHandle('blog_entry'); //by a page type handle

$pageList->filterByPageTypeHandle(['blog_entry', 'press_release']); //by page typeS
$pageList->filterByExcludeNav(true); //by an attribute

$topicNode = \Concrete\Core\Tree\Node::getByID(24); 
$pageList->filterByBlogEntryTopic($topicNode); //by a topic

$pageList->filterBySelectAttribute($akHandle, $value); //select attribute

$pageList->filterByUserID($uID); //by user ID
$pageList->filterByIsApproved($cvIsApproved); //by is approved
$pageList->filterByIsAlias($ia); //by alias

$pageList->filterByDateAdded($date, $comparison = '='); //by date added
$pageList->filterByPublicDate($date, $comparison = '='); //by public date
$pageList->filterByDateLastModified($date, $comparison = '='); //by last modified date
$pageList->filterByNumberOfChildren($num, $comparison = '>'); //by number of children
```

#### Sort a page list
```PHP
$pageList->sortByRelevance()

$pageList->sortByDisplayOrder();
$pageList->sortByDisplayOrderDescending()

$pageList->sortByCollectionIDAscending()

$pageList->sortByPublicDate();
$pageList->sortByPublicDateDescending();

$pageList->sortByName();
$pageList->sortByNameDescending();

$pageList->sortBy('ak_attribute_handle', 'desc'); //by an attribute: 'ak_' + attrbute_handle
```

### Page operations


#### Add a page
```PHP
//$parentPage = \Page::getByID(1);
$parentPage = \Page::getByPath('/blog');
$pageType = \PageType::getByHandle('blog_entry'); //dashboard/pages/types 
$pageTemplate = \PageTemplate::getByHandle('blog_entry');//dashboard/pages/templates
$page = $parentPage->add(
    $pageType, 
    array(
        'cName' => 'Hello All!',
        'cDescription' => 'Just a quick blog post.',
    	'cHandle ' => 'hello-all',
    	//'cDatePublic' => '2019-01-02 20:21:22',
    	//'cDateCreated' => date('Y-m-d H:i:s'),
    	//'pkgID ' => 1,
    	//'uID ' => 1,
    ),
    $pageTemplate
);
```

#### Update a page
```PHP
$page->update(
    array(
        'cName' => 'My new page name',
        'cDescription' => 'My new page description', 
    	//'cDatePublic' => '2019-01-02 20:21:22',
    	//'cDateCreated' => date('Y-m-d H:i:s'),
    	//'pkgID' => 1,
        //'uID' => 1,
        
        //'pTemplateID' => 1,
        //'cHandle' => 'new-handle',
        //'cCacheFullPageContent' => FALSE,
        //'cCacheFullPageContentOverrideLifetime' => FALSE,
        //'cCacheFullPageContentLifetimeCustom' => FALSE,
));
```

#### Delete a page
```PHP
$page->delete(); //delete it immediately
$page->moveToTrash(); //move to trash
```

#### Move a page
```PHP
$moveTo = \Page::getByPath('/archives');
$page->move($moveTo);
```

#### Copy a Page
```PHP
$copyTo = \Page::getByPath('/archives');
$page->duplicate($copyTo);
```

#### Add an extra location URL
```PHP
//$page = \Page::getByID(1);
$page = \Page::getByPath('/blog');
$page->addAdditionalPagePath('/blog-path-for-others');
```

#### Set/Update an attribute of a page
```PHP
$page = \Page::getByID(1); //by ID
$page->setAttribute('attribute_handle', 'value');
```

#### Clear an attribute of a page
```PHP
$page = \Page::getByID(1); //by ID
$page->clearAttribute('attribute_handle');
```

#### Refresh page cache
```PHP
$page = \Page::getByID(1); //by ID
$page->refreshCache();
```


## Files



### A Files


#### Get a file by a unique identifier
```PHP
$file = \File::getByID(1); //by ID
```

#### Get a file data
```PHP
echo $file->getFileID(); //file ID
echo $file->getFileName(); //file name

echo $file->getURL(); //direct url
echo $file->getDownloadURL(); //tracked url
echo $file->getRelativePath();echo "<br><br>";
echo $_SERVER['DOCUMENT_ROOT'].$file->getRelativePath();echo "<br><br>";

echo $file->getTitle();
echo $file->getDescription();
echo $file->getTags(); //string
print_r($file->getTagsList()); //array

echo $file->getSize();
echo $file->getFullSize();
echo $file->getExtension();
echo $file->getType();
echo $file->getMimeType();
echo $file->getDisplayType();
echo $file->getGenericTypeText();

echo $file->getAttribute('width');
echo $file->getAttribute('height');
echo $file->getAttribute('duration');

//file version
$fileVersion = $file->getApprovedVersion();
```

#### Get a file attribute
```PHP
echo $file->getAttribute('width');
```

#### Get list of attributes of a file
```PHP

```

### List of files


#### Get list of files
```PHP
$fileList = new FileList();

$files = $fileList->getResults();

//echo count($files);
foreach ((array)$files as $file) {
    echo $file->getFileID();
}
```

#### Get list of files with pagination
```PHP
$fileList = new FileList();

$pagination = $fileList->getPagination();
$pagination->setMaxPerPage(10);
$pagination->setCurrentPage(1);
$files = $pagination->getCurrentPageResults();

//Pagination functions
echo $pagination->getTotalResults(); //total number of results
echo $pagination->getTotalPages(); //total number of files
echo $pagination->hasNextPage(); //To determine whether paging is necessary
echo $pagination->hasPreviousPage(); //"
echo $pagination->renderDefaultView(); //Outputs HTML for Bootstrap 3. 

//echo count($files);
foreach ((array)$files as $file) {
    echo $file->getFileID();
}
```
For custom markup check [`here`](https://documentation.concrete5.org/tutorials/styling-the-pagination-5-7)

#### Filter a file list
```PHP
$FileList->filterByType(\Concrete\Core\File\Type\Type::T_IMAGE); //by type (T_IMAGE, T_TEXT, T_AUDIO, T_DOCUMENT, T_APPLICATION, T_UNKNOWN)
$FileList->filterByExtension('png'); //by extension
$FileList->filterByKeywords('foobar'); //by keywords
$FileList->filterBySize(1024, 2048); //Only includes files that are between 1MB and 2MB in Size
$FileList->filterByAttribute('width', 200, '>='); //Only include files where "width" is 200 or greater.
$FileList->filterByDateAdded($date, $comparison = '='); //by date added
$FileList->filterByTags($tags); //by tags

//SET
if ($fileSet) $FileList->filterBySet($fileSet); //by set (check 'Get a file set' for how to get a set)
$FileList->filterByNoSet(); //files in No Sets
```

#### Get files inside a folder
```PHP
//use Concrete\Core\Tree\Node\Type\FileFolder;
//use Concrete\Core\File\FolderItemList;

$fileFolder = FileFolder::getNodeByName('Folder Name');
$fileList = new FolderItemList();
if ($fileFolder) { 
    $fileList->filterByParentFolder($fileFolder);
    $files = $fileList->getResults();
}	

//echo count($files);
foreach ((array)$files as $file) {
    $file = $file->getTreeNodeFileObject();
    echo $file->getFileID();
}
```

#### Sort a file list
```PHP
$FileList->sortByFilenameAscending();
$FileList->sortByFileSetDisplayOrder();
```

#### Get a file set
```PHP
$fileSet = FileSet::getByID(1); //by ID
$fileSet = FileSet::getByName('File Set Name'); //name
```

#### Get a file folder
```PHP
$folder = Node::getByID($folderID); //by ID
$folder = Node::getNodeByName('My Folder'); //by name, not working
```

### File Operation


#### Importing a file
```PHP
$filePath = 'path/to/file/filename.jpg';
if (file_exists($filePath)) {
    $importer = new \Concrete\Core\File\Importer();
    $fileVersion = $importer->import($filePath, false); //echo get_class($fileVersion); //file version object
    $file = $fileVersion->getFile(); //echo get_class($file); //file object
}	
```

#### Delete a file
```PHP
$file = File::getByID(1);
$file->delete();
```

#### Set/Update an attribute to a file
```PHP
$file = File::getByID(1);
$file->setAttribute('attribute_handle', 'value');
```

#### Clear an attribute of a file
```PHP
$file = File::getByID(1);
$file->clearAttribute('attribute_handle');
```

#### Create a file set
```PHP
$fileSet = Set::createAndGetSet('My File Set', Set::TYPE_PUBLIC);
```

#### Add a file to a set
```PHP    
$file = \File::getByID(1); // by ID
$fileSet->addFileToSet($file);
```

#### Create a file folder
```PHP
//use Concrete\Core\File\Filesystem;

$filesystem = new Filesystem();
$folder = $filesystem->getRootFolder();
$folderName = 'My Folder - '.time();
$folder = $filesystem->addFolder($folder, $folderName);	
```

#### Add a file to a folder
```PHP    
$file = \File::getByID(1); // by ID
$fileNode = $file->getFileNodeObject();
if (is_object($fileNode)) $fileNode->move($folder);    
```

## Users



### A User

#### Get/Check current user
```PHP
$u = new User();

if ($u->isRegistered()) {
    print 'User is logged in.';
}

if ($u->isSuperUser()) {
    print 'Yes, they are!';
}

print $u->getUserID();

$groups = $u->getUserGroups();
foreach($groups as $groupID) {
    $group = \Concrete\Core\User\Group\Group::getByID($groupID);
    print $group->getGroupName();
}
```

#### Get a user by a unique identifier
```PHP
$user = User::getByUserID(1); //by ID
//User::getByUserID(3, true); // Now user 3 is logged in.
```



#### Get a user data
```PHP
$userGroups = $user->getUserGroups(); //print_r($userGroups);
$userIsActive = $user->isActive(); //print_r($userIsActive);
$userIsSuperUser = $user->isSuperUser(); //print_r($userIsSuperUser);
$userLastOnline = $user->getLastOnline(); //print_r(date('Y-m-d H:i:s', $userLastOnline));
$userUserName = $user->getUserName(); //print_r($userUserName);
$userIsRegistered = $user->isRegistered(); //print_r($userIsRegistered);
$userUserID = $user->getUserID(); //print_r($userUserID);
$userTimezone = $user->getUserTimezone(); //print_r($userTimezone);
```

#### Get user info object
```PHP
$ui = UserInfo::getByID(1); //by ID
$ui = UserInfo::getByUserName('admin'); //by username
$ui = UserInfo::getByEmail('jane@concrete5.org'); //by email
```

#### Get user info data
```PHP
$uiIsActive = $ui->isActive(); //echo $uiIsActive;
$uiUserName = $ui->getUserName(); //echo $uiUserName;
$uiEmail = $ui->getUserEmail(); //echo $uiEmail;
$uiNumLogins = $ui->getNumLogins(); //echo $uiNumLogins;
$uiLastIPAddress = $ui->getLastIPAddress(); //echo $uiLastIPAddress;
$uiLastLogin = $ui->getLastLogin(); //echo date('Y-m-d H:i:s', $uiLastLogin);
$uiPreviousLogin = $ui->getPreviousLogin(); //echo date('Y-m-d H:i:s', $uiPreviousLogin);
$uiPublicProfileUrl = $ui->getUserPublicProfileUrl(); //echo $uiPublicProfileUrl;
$uiHasAvatar = $ui->hasAvatar(); //echo $uiHasAvatar;
$uiAvatar = $ui->getUserAvatar(); //echo $uiAvatar->getPath();
```

#### Get a user (info) attributes
```PHP
$uiAttr = $ui->getAttribute('attribute_handle'); //echo $uiAttr;
```

### List of users


#### Get list of users
```PHP
$userList = new UserList();

$users = $userList->getResults();

//echo count($users);
foreach ((array)$users as $user) {
    echo $user->getUserID();
}
```

#### Get list of users with pagination
```PHP
$userList = new UserList();

$pagination = $userList->getPagination();
$pagination->setMaxPerPage(10);
$pagination->setCurrentPage(1);
$users = $pagination->getCurrentPageResults();

//Pagination functions
echo $pagination->getTotalResults(); //total number of results
echo $pagination->getTotalPages(); //total number of pages
echo $pagination->hasNextPage(); //To determine whether paging is necessary
echo $pagination->hasPreviousPage(); //"
echo $pagination->renderDefaultView(); //Outputs HTML for Bootstrap 3.

//echo count($users);
foreach ((array)$users as $user) {
    echo $user->getUserID();
}
```

#### Filter a user list
```PHP
$userList->filterByKeywords('andrew'); //by keywords (simple)
$userList->filterByFulltextKeywords('foobar'); //by keywords (advanced)
$userList->filterByUsername('foobar'); //by username
$userList->filterByFuzzyUsername('foobar'); //by username(fuzzy)
$userList->filterByDateAdded($date, $comparison = '='); //by date added
$userList->includeInactiveUsers();
$userList->includeUnvalidatedUsers();
$userList->filterByIsActive($isActive);
$userList->filterByIsValidated($isValidated);

$userList->filterByGroup('Administrators'); //by group
//OR send the group object
$group = \Group::getByName('Administrators');
$userList->filterByGroup($group);

$group = \Group::getByName('Administrators');
$userList->filterByGroup($group, false); //return all non-admins

$userList->filterByProfilePrivateMessagesEnabled(true); //by attribute

$userList->filterByInAnyGroup($groups, $inGroups = true) //multiple group
```

#### Sort a user list
```PHP
$userList->sortByDateAdded();
$userList->sortByUserName();

$userList->sortBy('ak_attribute_handle', 'desc'); //by an attribute: 'ak_' + attrbute_handle
```

### User operation


#### Add a user
```PHP
$ui = \UserInfo::add(array(
    'uName' => 'andrew',
    'uEmail' => 'andrew@concrete5.org', 
    'uPassword' => 'kittens',
    //'uDefaultLanguage' => '', //an ISO language code for the user's default language
    //'uIsValidated' => '', //whether the user is validated. 1 for validated, 0 for definitely unvalidated, and -1 for unknown (which is the default on sites that don't employ user validation
));
```

#### Update a user
```PHP
$ui = \UserInfo::getByID(10);
if ($ui) {
    $ui->update(array(
        //'uName' => 'andrew',
        //'uEmail' => 'new@email.com',
        //'uPassword' => 'kittens',
        //'uDefaultLanguage' => ''
        //'uIsValidated' => '',
        //'uTimezone' => 'America/Los_Angeles'
        //'uHasAvatar' => '',
        //'uPasswordConfirm' => '',
    ));
}

//change password
$ui = \UserInfo::getByID(10);
if ($ui) {
    $ui->update(array(
        'uPassword' => 'newpass', 
        'uPasswordConfirm' => 'newpass']
    ));
}
```

#### Activate/Deactivate a user
```PHP
$ui = \UserInfo::getByID(20);
if ($ui) {
    $ui->deactivate();
    $ui->activate();
}    
```

#### Delete a user
```PHP
$ui = \UserInfo::getByID(10);
if ($ui) {
    $ui->delete();
}
```

#### Set/Update an attribute to a user
```PHP
$ui = UserInfo::getByID(1); //by ID
if ($ui) {
    $ui->setAttribute('attribute_handle', 'value');
}    
```

#### Clear an attribute of a user
```PHP
$ui = UserInfo::getByID(1); //by ID
if ($ui) {
    $ui->clearAttribute('attribute_handle');
}    
```

## Attributes



### Attribute operations


#### Add an attribute
```PHP
//use CollectionAttributeKey;
//use Concrete\Core\Attribute\Type as AttributeType;

$key = CollectionAttributeKey::getByHandle('attr_handle');
if (!is_object($key)) {
    $attr_type = AttributeType::getByHandle('text'); 
    //$attr_type = AttributeType::getByHandle('number'); 
    //$attr_type = AttributeType::getByHandle('boolean'); //checkbox 
    //$attr_type = AttributeType::getByHandle('textarea'); 
    //$attr_type = AttributeType::getByHandle('image_file');
    //$attr_type = AttributeType::getByHandle('date_time'); 
    //$attr_type = AttributeType::getByHandle('url'); 

    $desc = array ( 
        'akHandle' => 'attr_handle',
        'akName'=> t('Attribute Name'),
        //'asID' => $attrSetID, //attribute set ID: check 'Get a set/Create a set' on how to get $attrSetID
        //'akIsSearchableIndexed' => TRUE, //Content included in search index
        //'akIsSearchable' => TRUE, //Field available in advanced search
        
        //textarea attribute
        //'akTextareaDisplayMode' => 'rich_text', //ONLY FOR 'textarea': Input Format/ values: text,rich_text

        //date_time attribute
        //'akUseNowIfEmpty' => TRUE, //ONLY FOR 'date_time': Suggest the current date/time if empty/ values: TRUE, FALSE
        //'akDateDisplayMode' => 'date_time', //ONLY FOR 'date_time': Ask User For/ values: date_time, date, date_text, text
        //'akTextCustomFormat' => 'Y-m-d H:i:s', //ONLY FOR 'date_time': Custom format/ values: PHP date function values
        //'akTimeResolution' => 60, //ONLY FOR 'date_time': Time Resolution/ values: 1, 5, 10, 15, 30, 60, 300, 600, 900, 1800, 3600, 10800, 14400, 21600, 43200
    );
    $key = CollectionAttributeKey::add( $attr_type, $desc, $pkg = null);

    //option list attrbute
    //$keyOption = SelectAttributeTypeOption::add($key, 'Option 1'); //add options
    //$keyOption = SelectAttributeTypeOption::add($key, 'Option 2'); //"
}
```

#### Delete an attribute
```PHP

```

#### List of attribute set categories (collection/user/file/site/event)
```PHP
//use Concrete\Core\Attribute\Key\Category as AttributeKeyCategory;
$categories = AttributeKeyCategory::getList();		
foreach ((array)$categories as $category) {
    $categoryID = $category->getAttributeKeyCategoryID(); //echo $categoryID;
    $categoryHandle = $category->getAttributeKeyCategoryHandle(); //echo $categoryHandle;
}
```

#### List of sets in a category
```PHP
//use Concrete\Core\Attribute\Key\Category as AttributeKeyCategory;
$categoryID = 1; 
$category = AttributeKeyCategory::getByID($categoryID);
if (is_object($category)) {
    $sets = $category->getController()->getSetManager()->getAttributeSets();
    foreach ((object)$sets as $set) {
        $setID = $set->getAttributeSetID(); //echo $setID);
        $setHandle = $set->getAttributeSetHandle(); //echo $setHandle;
        $setName = $set->getAttributeSetDisplayName(); //echo $setName;
	}
}	
```

#### Get a Collection/Page attribute
```PHP
$attr = CollectionAttributeKey::getByID(1); //by ID
$attr = CollectionAttributeKey::getByHandle('attribute_handle'); //by handle

$attrID = $attr->getAttributeKeyID(); //echo $attrID;
$attrHandle = $attr->getAttributeKeyHandle(); //echo $attrHandle;
$attrName = $attr->getAttributeKeyName(); //echo $attrName;
```

#### Get options of an 'Option List' attribute
```PHP
$attr = CollectionAttributeKey::getByHandle('attribute_handle'); //by handle
$controller = $attr->getController();
$attrOptions = $controller->getOptions();
foreach ((object)$attrOptions as $attrOption) {
    $attrOptionID = $attrOption->getSelectAttributeOptionID(); //echo $attrOptionID;
    $attrOptionValue = $attrOption->getSelectAttributeOptionValue(); //echo $attrOptionValue;
}
```

### Attrubute Set


#### A set
```PHP
$attrSet = AttributeSet::getByID('attribute_set_id'); //by ID
$attrSet = AttributeSet::getByHandle('attribute_set_handle'); //by handle
```

#### Attributes in a set
```PHP
$attrs = $attrSet->getAttributeKeys();
foreach($attrs as $attr) {
    $attrID = $attr->getAttributeKeyID(); //echo $attrID;
    $attrHandle = $attr->getAttributeKeyHandle(); //echo $attrHandle;
    $attrName = $attr->getAttributeKeyName(); //echo $attrName;
}
```

#### Add a Collection/Page set
```PHP
//use Concrete\Core\Attribute\Key\Category as AttributeKeyCategory;

$akc = AttributeKeyCategory::getByHandle('collection');
$akc->setAllowAttributeSets(AttributeKeyCategory::ASET_ALLOW_SINGLE);
$attrSet = $akc->addSet('my_set', t('My Set'), $pkg = null, $locked = null); 
    
$attrSetID = $attrSet->getAttributeSetID(); //echo $attrSetID;
$attrSetHandle = $attrSet->getAttributeSetHandle(); //echo $attrSetHandle;
$attrSetName = $attrSet->getAttributeSetName(); //echo $attrSetName;
```

#### Add a File set
```PHP
```



#### List of sets
```PHP
```

## Themes



### Page types


#### Adding areas in a Page Template
```PHP
//regular area
$a = new Area("Main");
//$a->enableGridContainer(); //enable grid container in area
//$a->setAreaGridMaximumColumns(12);
//if ($c->isEditMode()); //do something
//if ($a->getTotalBlocksInArea($c) > 0); //do something
$a->display($c);

//global area
$a = new GlobalArea("Main");
$a->display();
```

#### Embedding Blocks in a Page Template
```PHP
$bt = BlockType::getByHandle('block_handle');
$bt->controller->field1 = 'field1';
$bt->render(); //render default template: view.php
//$bt->render('templates/my_template'); //render specific template: my_template.php
```


## Single Pages



## Blocks



## Stacks



## Packages



## Express Entries



## Language



## Constants



## Configs



## Helpers

#### General
```PHP
//\concrete\bootstrap\helpers.php

//Translate text (simple form).
t($text);

//Translate text (plural form).
t2($singular, $plural, $number);

//Translate text (simple form) with a context.
tc($context, $text);

//Security helper.
h($input);

//Returns $string in CamelCase.
camelcase($string, $leaveSlashes = false);

//Returns CamelCase string as camel_case.
uncamelcase($string);

//Fills an object properties from an array.
array_to_object($o, $array);

//Dumps information about a variable in a way that can be used with Doctrine recursive objects.).
var_dump_safe($o, $echo = true, $maxDepth = true);

//Generate the PHPDoc for a set of defined variables.
output_vars(array $get_defined_vars, $valueOfThis = null, $return = false);
```

#### Number helper
```PHP
$in = Core::make('helper/number');

$im->flexround($value); //Rounds the value only out to its most significant digit.
$im->trim($value); //Remove superfluous zeroes from a string containing a number.
$im->isNumber($string); //Checks if a given string is valid representation of a number in the current locale.
$im->isInteger($string); //Checks if a given string is valid representation of an integer in the current locale.
$im->format($number, $precision = null); //Format a number with grouped thousands and localized decimal point/thousands separator.
$im->unformat($string, $trim = true, $precision = null); //Parses a localized number representation and returns the number (or null if $string is not a valid number representation).
$im->formatSize($size, $forceUnit = ''); //Formats a size (measured in bytes, KB, MB, ...).
$im->getBytes($val); //Nice and elegant function for converting memory. Thanks to @lightness races in orbit on Stackoverflow.

//\concrete\src\Utility\Service\Number.php
```

#### Text helper
```PHP
$th = Core::make('helper/text');

$th->encodePath($path); //URL-encodes collection path.
$th->match($pattern, $value); //Determine if a given string matches a given pattern.
$th->lugSafeString($handle, $maxlength = 128); //Remove unsafe characters for URL slug.
$th->sanitize($string, $max_length = 0, $allowed = ''); //Strips tags and optionally reduces string to specified length.
$th->email($email); //Leaves only characters that are valid in email addresses (RFC).
$th->alphanum($string); //Leaves only characters that are alpha-numeric.
$th->entities($v); //always use in place of htmlentites(), so it works with different languages.
$th->decodeEntities($v); //Decodes html-encoded entities (for instance: from '&gt;' to '>').
$th->specialchars($v); //A concrete5 specific version of htmlspecialchars(). Double encoding is OFF, and the character set is set to your site's.
$th->shorten($textStr, $numChars = 255, $tail = '…'); //An alias for shorten().
$th->shortText($textStr, $numChars = 255, $tail = '…'); //Like sanitize, but requiring a certain number characters, and assuming a tail.
$th->camelcase($string); //Takes a string and turns it into the CamelCase or StudlyCaps version.
$th->twitterAutolink($input, $newWindow = 0, $withSearch = 0); //automatically add hyperlinks to any twitter style @usernames in a string.
$th->makenice($input); //Runs a number of text functions, including autolink, nl2br, strip_tags. Assumes that you want simple text comments but with a few niceties.
$th->prettyStripTags($input, $allowedTags = null); //Runs strip_tags but ensures that spaces are kept between the stripped tags.
$th->autolink($input, $newWindow = false, $defaultProtocol = 'http://'); //Scans passed text and automatically hyperlinks any URL inside it.
$th->fnmatch($pattern, $string); //A wrapper for PHP's fnmatch() function, which some installations don't have.
$th->uncamelcase($string); //Takes a CamelCase string and turns it into camel_case.
$th->unhandle($string); //Takes a handle-based string like "blah_blah" or "blah-blah" or "blah/blah" and turns it into "Blah Blah".
$th->handle($handle, $leaveSlashes = false); //Takes a string and turns it into a handle.
$th->sanitizeFileSystem($handle); //Determines whether a string matches a particular pattern.
$th->urlify($handle, $max_length = null, $locale = '', $removeExcludedWords = true); //Takes text and returns it in the "lowercase-and-dashed-with-no-punctuation" format.
$th->asciify($text, $locale = ''); //Takes text and converts it to an ASCII-only string (characters with code between 32 and 127, plus \t, \n and \r).
$th->wordSafeShortText($textStr, $numChars = 255, $tail = '…'); //alias of shortenTextWord().
$th->shortenTextWord($textStr, $numChars = 255, $tail = '…'); //Shortens and sanitizes a string but only cuts at word boundaries.
$th->filterNonAlphaNum($val); //Strips out non-alpha-numeric characters.
$th->highlightSearch($value, $searchString); //Highlights a string within a string with the class ccm-highlight-search.
$th->formatXML($xml); //Formats a passed XML string nicely.
$th->appendXML(\SimpleXMLElement $root, \SimpleXMLElement $new); //Appends a SimpleXMLElement to a SimpleXMLElement.

//\concrete\src\Utility\Service\Text.php
```

#### URL helper
```PHP
$uh = Core::make('helper/url');

$uh->setVariable($variable, $value = false, $url = false); //
$uh->unsetVariable($variable, $url = false); //
$uh->buildQuery($url, $params); //
$uh->shortenURL($strURL); //Shortens a given url with the tiny url api.

//\concrete\src\Utility\Service\Url.php
```

#### Array helper
```PHP
$ah = Core::make('helper/array');

$ah->get(array $array, $keys, $default = null); //Fetches a value from an (multidimensional) array.
$ah->set(array $array, $keys, $value); //Sets a value in an (multidimensional) array, creating the arrays recursivly.
$ah->parseKeys($keys); //Turns the string keys into an array of keys.
$ah->flatten(array $array); //Takes a multidimensional array and flattens it.
$ah->subset($a, $b); //Returns whether $a is a proper subset of $b.

//\concrete\src\Utility\Service\Array.php
```

#### Arrays validation helper
```PHP
$avh = Core::make('helper/validation/arrays');

$avh->containsString($needle, $haystack = array(), $recurse = true); //Returns true if any string in the "haystack" contains the "needle".

//\concrete\src\Utility\Service\Validation\Arrays.php
```

#### Numbers validation helper
```PHP
$nvh = Core::make('helper/validation/numbers');

$nvh->integer($data, $min = null, $max = null); //Tests whether the passed item is an integer.
$nvh->number($data, $min = null, $max = null); //Tests whether the passed item is an integer or a floating point number.

//\concrete\src\Utility\Service\Validation\Numbers.php
```

#### Strings validation helper
```PHP
$nvh = Core::make('helper/validation/strings');

$svh->email($em, $testMXRecord = false, $strict = false); //@deprecated Use Concrete\Core\Validator\String\EmailValidator
$svh->alphanum($value, $allowSpaces = false, $allowDashes = false); //Returns true on whether the passed string is completely alpha-numeric, if the value is not a string or is an empty string false will be returned.
$svh->handle($handle); //Returns true if the passed string is a valid "handle" (e.g. only letters, numbers, or a _ symbol).
$svh->notempty($field); //Returns false if the string is empty (including trim()).
$svh->min($str, $length); //Returns true on whether the passed string is larger or equal to the passed length.
$svh->max($str, $length); //Returns true on whether the passed is smaller or equal to the passed length.
$svh->containsNumber($str); //Returns 0 if there are no numbers in the string, or returns the number of numbers in the string.
$svh->containsUpperCase($str); //Returns 0 if there are no upper case letters in the string, or returns the number of upper case letters in the string.
$svh->containsLowerCase($str); //Returns 0 if there are no lower case letters in the string, or returns the number of lower case letters in the string.
$svh->containsSymbol($str); //Returns 0 if there are no symbols in the string, or returns the number of symbols in the string.

//\concrete\src\Utility\Service\Validation\Strings.php
```

#### JSON helper
```PHP
$jh = Core::make('helper/json');

$jh->decode($string, $assoc = false); //Decodes a JSON string into a php variable.
$jh->encode($mixed); //Encodes a data structure into a JSON string.

//\concrete\src\Http\Service\Json.php
```

#### Ajax helper
```PHP
$ah = Core::make('helper/json');

$ah->isAjaxRequest(Request $request); //Check if a request is an Ajax call.
$ah->sendResult($result); //Sends a result to the client and ends the execution.
$ah->sendError($error); //Sends an error to the client and ends the execution.

//\concrete\src\Http\Service\Ajax.php
```


#### HTML helper
```PHP
$hh = Core::make('helper/html');

$hh->css($file, $pkgHandle = null); //
$hh->javascript($file, $pkgHandle = null); //
$hh->noFollowHref($input); //Takes in a string, and adds rel="nofollow" to any a tags that contain an href attribute.

//\concrete\src\Html\Service\Html.php
```

#### Date helper
```PHP
$dh = Core::make('helper/date'); 
//$dh = Core::make('date');

$dh->toDB($value = 'now', $fromTimezone = 'system'); //Convert any date/time representation to a string that can be used in DB queries.
$dh->getOverridableNow($asTimestamp = false); //Return the date/time representation for now, that can be overridden by a custom request when viewing pages in a moment specified by administrators (custom request date/time).
$dh->date($mask, $timestamp = false, $toTimezone = 'system'); //Subsitute for the native date() function that adds localized date support.
$dh->getTimezoneName($timezoneID); //Retrieve the display name (localized) of a time zone given its PHP identifier.
$dh->getTimezones(); //Returns a keyed array of timezone identifiers (keys are the standard PHP timezone names, values are the localized timezone names).
$dh->getGroupedTimezones(); //Returns the list of timezones with translated names, grouped by region.
$dh->getTimezoneDisplayName($timezone); //Returns the display name of a timezone.
$dh->timeSince($posttime, $precise = false); //Describe the difference in time between now and a date/time in the past.
$dh->describeInterval($diff, $precise = false); //Returns the localized representation of a time interval specified as seconds.
$dh->getTimezoneID($timezone); //Returns the normalized timezone identifier.
$dh->getUserTimeZoneID(); //
$dh->getTimezone($timezone); //Returns a \DateTimeZone instance for a specified timezone identifier.
$dh->toDateTime($value = 'now', $toTimezone = 'system', $fromTimezone = 'system'); //Convert a date to a \DateTime instance.
$dh->getDeltaDays($from, $to, $timezone = 'user'); //Returns the difference in days between to dates.
$dh->formatDate($value = 'now', $format = 'short', $toTimezone = 'user'); //Render the date part of a date/time as a localized string.
$dh->formatTime($value = 'now', $withSeconds = false, $toTimezone = 'user'); //Render the time part of a date/time as a localized string.
$dh->formatDateTime($value = 'now', $longDate = false, $withSeconds = false, $toTimezone = 'user'); //Render both the date and time parts of a date/time as a localized string.
$dh->formatPrettyDate($value, $longDate = false, $toTimezone = 'user'); //Render the date part of a date/time as a localized string. If the day is yesterday we'll print 'Yesterday' (the same for today, tomorrow).
$dh->formatPrettyDateTime($value, $longDate = false, $withSeconds = false, $timezone = 'user'); //Render both the date and time parts of a date/time as a localized string. If the day is yesterday we'll print 'Yesterday' (the same for today, tomorrow).
$dh->formatCustom($format, $value = 'now', $toTimezone = 'user', $fromTimezone = 'system'); //Render a date/time as a localized string, by specifying a custom format.
$dh->getJQueryUIDatePickerFormat($relatedPHPFormat = ''); //Returns the format string for the jQueryUI DatePicker widget
$dh->getTimeFormat(); //Returns the time format (12 or 24).
$dh->getPHPDatePattern(); //
$dh->getPHPTimePattern(); //Get the PHP date format string for times.
$dh->getPHPDateTimePattern(); //Get the PHP date format string for dates/times.
$dh->getLocalDateTime($systemDateTime = 'now', $mask = null); //@deprecated
$dh->getSystemDateTime($userDateTime = 'now', $mask = null); //@deprecated
$dh->dateTimeFormatLocal($datetime, $mask); //@deprecated

//\concrete\src\Localization\Service\Date.php
```

#### Image helper
```PHP
$ih = Core::make('helper/image');

$ih->getStorageLocation(); //
$ih->setStorageLocation(StorageLocationInterface $storageLocation); //
$ih->setJpegCompression($level); //
$ih->getJpegCompression(); //
$ih->setPngCompression($level); //
$ih->getPngCompression(); //
$ih->setThumbnailsFormat($thumbnailsFormat); //
$ih->getThumbnailsFormat(); //
$ih->create($mixed, $savePath, $width, $height, $fit = false, $format = false); //
$ih->returnThumbnailObjectFromResolver($obj, $maxWidth, $maxHeight, $crop = false); //Checks thumbnail resolver for filename, schedule for creation via ajax if necessary.
$ih->checkForThumbnailAndCreateIfNecessary($obj, $maxWidth, $maxHeight, $crop = false); //Checks filesystem for thumbnail and if file doesn't exist will create it immediately. concrete5's default behavior from the beginning up to 8.1.
$ih->processThumbnail($async, $obj, $maxWidth, $maxHeight, $crop); //
$ih->getThumbnail($obj, $maxWidth, $maxHeight, $crop = false); //
$ih->outputThumbnail($mixed, $maxWidth, $maxHeight, $alt = null, $return = false, $crop = false); //

//\concrete\src\File\Image\BasicThumbnailer.php
```






## System Operations



### Database


#### Current database
```PHP
//database connection
$db = Database::connection();

//prepare any query
$statement = $db->executeQuery('SELECT * FROM `myTable` WHERE `id`>?;', array(0)); 
	
//echo $statement->rowCount(); //number of SELECTed/UPDATEd/DELETEd rows
//echo $statement->getSqlQuery(); //prepared SQL //not working

//iterate through rows
$rows = $statement->fetchAll(); //print_r($rows);
foreach ($rows as $row) {
    print_r($row);
}
//OR:
while ($row = $statement->fetch()) {
    //print_r($row);
}	

//get associated rows
$row = $db->fetchAssoc('SELECT * FROM `myTable` WHERE `id` = ?;', array(1)); //print_r($row);

//get rows diretly
$rows = $db->fetchAll('SELECT `name` FROM `myTable`;'); //print_r($rows);

//get a column
$column = $db->fetchColumn('SELECT `name` FROM `myTable` WHERE id = ?;', array($id)); //echo $column;


//UPDATE
$statement = $db->executeQuery('UPDATE `myTable` SET name = ? WHERE `id` = ?;', array('new name', 1)); 
//echo $statement->rowCount(); //number of affected rows

//DELETE
$statement = $db->executeQuery('DELETE FROM `myTable` WHERE `id` = ?;', array(1)); 
//echo $statement->rowCount(); //number of affected rows
```
For more check [`here`](https://www.doctrine-project.org/api/dbal/2.5/Doctrine/DBAL/Connection.html)

#### Another database
```PHP
//new database connection info in /appilication/config/database.php
return array(
    'default-connection' => 'concrete',
    'connections' => array(
        'concrete' => array(
            'driver' => 'c5_pdo_mysql',
            'server' => 'localhost',
            'database' => 'database',
            'username' => 'username',
            'password' => 'password',
            'charset' => 'utf8',
        ),
        'pricing' => array(
            'driver' => 'c5_pdo_mysql',
            'server' => 'secure-pricing.wherever.com',
            'database' => 'pricing_db',
            'username' => 'username',
            'password' => 'password',
            'charset' => 'utf8',
        ),
    ),
);

$dbPricing = Database::connection('pricing');
```

### Misc.

#### URL
```PHP
$url = URL::to('/path/to/somewhere'); //http://ursite/index.php/path/to/somewhere
```

#### Logging
```PHP
//use Log;
Log::addInfo('This is an informative message.');
Log::addWarning('Uh oh.');
Log::addAlert('Red alert!');
Log::addNotice('A notice error.');
//see logs at /dashboard/reports/logs
```

#### Get environment
```PHP
$environment = Core::make('app')->environment(); //echo $environment;
```

#### Clear site cache
```PHP
Core::make('app')->clearCaches();
//OR
$this->app->clearCaches();
//OR
//use Concrete\Core\Support\Facade\Application;
$app = Application::getFacadeApplication();
$app->make('app')->clearCaches();
```


## Contributors


