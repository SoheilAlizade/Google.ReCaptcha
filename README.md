# reCaptcha.Google.Mvc

Install Nuget Package:

`Install-Package reCaptcha.Google.Mvc -Version 1.0.1`

**Documention**

**configure Captcha**

In `Global.asax` file and `Application_Start` method you can config Google reCaptcha:

``
  GoogleCaptchaConfiguration.Register(new GoogleCaptchaConfig(CaptchaTheme.Light)
  {
      EnableInDebuggingMode = false,
      Secretkey = "yourSecretkey",
      Sitekey = "yourSitekey",
  });
``

**Usage**

To render Captcha use `Html.RenderCaptcha()`:

```
   @Html.RenderCaptcha()
   @Html.RenderCaptcha("siteKey") // also you set Sitekey here
```

To render Captcha script  use `Html.RenderCaptchaScript()`:

```
@Html.RenderCaptchaScript()
```

To validation request use `GoogleCaptcha` on the action method:

```
   [HttpPost]
   [Route("sing-up")]
   [GoogleCaptcha]
   public ActionResult Register()
   {
       // more code
   }
```





