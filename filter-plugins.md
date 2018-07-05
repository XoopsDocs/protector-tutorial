# Filter Plugins

There are two plugins distributed with the module. To install them, copy the files in XOOPS\_TRUST\_PATH/modules/protector/filters\_disabled/ into the adjacent /filters\_enabled folder.

**postcommon\_post\_deny\_by\_rbl.php**

An anti-SPAM plugin. All posts from IPs registered within RBL will be rejected. This plugin can slow the performance of posts, especially in chat modules.

**postcommon\_post\_need\_multibyte.php**

An anti-spam plugin that only works for multibyte Japanese, Traditional Chinese, Simplified Chinese and Korean language sites. Basically, posts without multi-byte characters will be rejected.

