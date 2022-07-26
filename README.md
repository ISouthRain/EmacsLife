# what is this ?
  Emacs Happy in Your Life.

  Wecome to you share Emacs happy Life, everything.

  分享你的 Emacs Happy 时刻, 任何都可以, 只要你认为有用.

# How to Share your Emacs happy ?
  Fork this and Pull Request. Thanks !!
# Org-mode
## Org-mode Use Gnupg
   **Emacs Org-mode and Gnupg encrypted data protect your privacy**
   <details>
<summary>code</summary>

   ``` elisp
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; org 标题加密， 只需添加 :crypt:
(use-package org-crypt
  :defer 4
  :ensure nil
  :config
(org-crypt-use-before-save-magic)
(setq org-tags-exclude-from-inheritance '("crypt"))
;; GPG ID, 解密一个文件可以知道这个ID
(setq org-crypt-key "885A586a9*******")
(setq auto-save-default nil)
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; Windows 用户使用加密的时候可能因为换行符的原因导致产生 ^M 无法加密, 可使用以下函数解密
;; 解决 ^M 解密问题
(defun freedom/org-decrypt-entry ()
  "Replace DOS eolns CR LF with Unix eolns CR"
  (interactive)
  (goto-char (point-min))
    (while (search-forward "\r" nil t) (replace-match ""))
  (org-decrypt-entry))
)
   ```
   
</details>
</details>
   0. (setq org-crypt-key "885A586a9*******")  

    ![GpgID](https://github.com/ISouthRain/EmacsLife/blob/main/Attachment/README/Org-mode/GpgID.png)  


   1. Open .gpg file can auto Encrypt or Decrypt
# License
  This software is provided by MIT License.
