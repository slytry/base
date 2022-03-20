---
aliases: null
date created: 2022-03-17 10:41
date updated:
---

### MJML

Структура начинается с тэга mjml, аналог HTML. Внутри могут быть только два компонента mj-head и mj-body.

Может принимать два атрибута:

* `owa` можно назначить `"desktop"`. Это принудительно отключит мобильный адаптив для старых версий outlook, в котором не поддерживаются медиа запросы
* `lang` аналог `<html lang="">`

### Section & column

Страницу делим на section ( `<mj-section>`) и внури могут быть колонки (`<mj-column>`). 
Даже если не нужны колонки должна быть хотябы одна колонка, на этом завязан адаптив.

Ширины section по умолчанию 600px. Это можно изменить в mj-body. В каждом отдельном section нельзя задавать ширину. Но можно задать ширину 100% [[mj-section|Подробнее]]

Ширина `<mj-column>` по умолчанию 100%. Это можно менять непосредствено для каждом колонки. 

>Если задать фиксированную	 600px то сгенирируется медиа запрос min-width на 480px. Начиная уже с такого экрана будет прописано правило width: 600px !important; То есть любой фиксирование значение ширины больше чем максимальная ширина контейнера (600 по умолчанию, можно переназначать) ломает адаптив. Стоит применять с остороожностью. Так же работает для любых других значений. Знаяение меньше контейнера просто ограничивают колонку по ширине, собственно.

Любой mj компонент внутри column по умолчанию будет тоже иметь ширину 100%. 


### Пример генерации
Такая разметка превратиться: 

```html
<mjml lang="ru">
  <mj-head> </mj-head>
  <mj-body width="400px">
    <mj-section background-color="#f7f734">
      <mj-column background-color="#fff">
        <mj-text>
          fsfsdf
        </mj-text>
      </mj-column>
    </mj-section>
    <mj-section background-color="#f7f734">
      <mj-column background-color="#fff">
        <mj-text>
          fsfsdf
        </mj-text>
      </mj-column>
    </mj-section>
  </mj-body>
</mjml>


```

В такую:

```html
<!DOCTYPE html>
<html
	lang="ru"
	xmlns="http://www.w3.org/1999/xhtml"
	xmlns:v="urn:schemas-microsoft-com:vml"
	xmlns:o="urn:schemas-microsoft-com:office:office"
>
	<head>
		<title></title>
		<!--[if !mso]><!-->
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<!--<![endif]-->
		<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
		<meta name="viewport" content="width=device-width,initial-scale=1" />
		<style type="text/css">
			#outlook a {
				padding: 0;
			}
			body {
				margin: 0;
				padding: 0;
				-webkit-text-size-adjust: 100%;
				-ms-text-size-adjust: 100%;
			}
			table,
			td {
				border-collapse: collapse;
				mso-table-lspace: 0pt;
				mso-table-rspace: 0pt;
			}
			img {
				border: 0;
				height: auto;
				line-height: 100%;
				outline: none;
				text-decoration: none;
				-ms-interpolation-mode: bicubic;
			}
			p {
				display: block;
				margin: 13px 0;
			}
		</style>
		<!--[if mso]>
			<noscript>
				<xml>
					<o:OfficeDocumentSettings>
						<o:AllowPNG />
						<o:PixelsPerInch>96</o:PixelsPerInch>
					</o:OfficeDocumentSettings>
				</xml>
			</noscript>
		<![endif]-->
		<!--[if lte mso 11]>
			<style type="text/css">
				.mj-outlook-group-fix {
					width: 100% !important;
				}
			</style>
		<![endif]-->
		<!--[if !mso]><!-->
		<link
			href="https://fonts.googleapis.com/css?family=Ubuntu:300,400,500,700"
			rel="stylesheet"
			type="text/css"
		/>
		<style type="text/css">
			@import url(https://fonts.googleapis.com/css?family=Ubuntu:300,400,500,700);
		</style>
		<!--<![endif]-->
		<style type="text/css">
			@media only screen and (min-width: 480px) {
				.mj-column-per-100 {
					width: 100% !important;
					max-width: 100%;
				}
			}
		</style>
		<style media="screen and (min-width:480px)">
			.moz-text-html .mj-column-per-100 {
				width: 100% !important;
				max-width: 100%;
			}
		</style>
		<style type="text/css"></style>
	</head>
	<body style="word-spacing: normal">
		<div>
			<!--[if mso | IE]><table align="center" border="0" cellpadding="0" cellspacing="0" class="" role="presentation" style="width:400px;" width="400" bgcolor="#f7f734" ><tr><td style="line-height:0px;font-size:0px;mso-line-height-rule:exactly;"><![endif]-->
			<div
				style="background: #f7f734; background-color: #f7f734; margin: 0px auto; max-width: 400px"
			>
				<table
					align="center"
					border="0"
					cellpadding="0"
					cellspacing="0"
					role="presentation"
					style="background: #f7f734; background-color: #f7f734; width: 100%"
				>
					<tbody>
						<tr>
							<td style="direction: ltr; font-size: 0px; padding: 20px 0; text-align: center">
								<!--[if mso | IE]><table role="presentation" border="0" cellpadding="0" cellspacing="0"><tr><td class="" style="vertical-align:top;width:400px;" ><![endif]-->
								<div
									class="mj-column-per-100 mj-outlook-group-fix"
									style="
										font-size: 0px;
										text-align: left;
										direction: ltr;
										display: inline-block;
										vertical-align: top;
										width: 100%;
									"
								>
									<table
										border="0"
										cellpadding="0"
										cellspacing="0"
										role="presentation"
										style="background-color: #ffffff; vertical-align: top"
										width="100%"
									>
										<tbody>
											<tr>
												<td
													align="left"
													style="font-size: 0px; padding: 10px 25px; word-break: break-word"
												>
													<div
														style="
															font-family: Ubuntu, Helvetica, Arial, sans-serif;
															font-size: 13px;
															line-height: 1;
															text-align: left;
															color: #000000;
														"
													>
														fsfsdf
													</div>
												</td>
											</tr>
										</tbody>
									</table>
								</div>
								<!--[if mso | IE]></td></tr></table><![endif]-->
							</td>
						</tr>
					</tbody>
				</table>
			</div>
			<!--[if mso | IE]></td></tr></table><table align="center" border="0" cellpadding="0" cellspacing="0" class="" role="presentation" style="width:400px;" width="400" bgcolor="#f7f734" ><tr><td style="line-height:0px;font-size:0px;mso-line-height-rule:exactly;"><![endif]-->
			<div
				style="background: #f7f734; background-color: #f7f734; margin: 0px auto; max-width: 400px"
			>
				<table
					align="center"
					border="0"
					cellpadding="0"
					cellspacing="0"
					role="presentation"
					style="background: #f7f734; background-color: #f7f734; width: 100%"
				>
					<tbody>
						<tr>
							<td style="direction: ltr; font-size: 0px; padding: 20px 0; text-align: center">
								<!--[if mso | IE]><table role="presentation" border="0" cellpadding="0" cellspacing="0"><tr><td class="" style="vertical-align:top;width:400px;" ><![endif]-->
								<div
									class="mj-column-per-100 mj-outlook-group-fix"
									style="
										font-size: 0px;
										text-align: left;
										direction: ltr;
										display: inline-block;
										vertical-align: top;
										width: 100%;
									"
								>
									<table
										border="0"
										cellpadding="0"
										cellspacing="0"
										role="presentation"
										style="background-color: #ffffff; vertical-align: top"
										width="100%"
									>
										<tbody>
											<tr>
												<td
													align="left"
													style="font-size: 0px; padding: 10px 25px; word-break: break-word"
												>
													<div
														style="
															font-family: Ubuntu, Helvetica, Arial, sans-serif;
															font-size: 13px;
															line-height: 1;
															text-align: left;
															color: #000000;
														"
													>
														fsfsdf
													</div>
												</td>
											</tr>
										</tbody>
									</table>
								</div>
								<!--[if mso | IE]></td></tr></table><![endif]-->
							</td>
						</tr>
					</tbody>
				</table>
			</div>
			<!--[if mso | IE]></td></tr></table><![endif]-->
		</div>
	</body>
</html>

```

---

###### Citation

