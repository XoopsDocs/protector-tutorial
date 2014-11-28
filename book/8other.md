# 8.0 Filter plugins

There are two plugins distributed with the module. To install them, copy the files in XOOPS_TRUST_PATH/modules/protector/filters_disabled/ into the adjacent /filters_enabled folder.

**postcommon_post_deny_by_rbl.php**

An anti-SPAM plugin. All posts from IPs registered within RBL will be rejected. This plugin can slow the performance of posts, especially in chat modules.

**postcommon_post_need_multibyte.php**

An anti-spam plugin that only works for multibyte Japanese, Traditional Chinese, Simplified Chinese and Korean language sites. Basically, posts without multi-byte characters will be rejected.
