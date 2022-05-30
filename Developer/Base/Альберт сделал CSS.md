```
@use 'vars' as *;
.compromise {
	width: 100%;
	min-height: 100vh;

	position: relative;

	&__space-holder {
		width: 100%;

		position: relative;
	}

	&__sticky {
		height: 100vh;
		width: 100%;

		position: sticky;
		top: 0;

		overflow-x: hidden;
		pointer-events: none;
	}

	&__horizontal {
		height: 100%;

		position: absolute;

		will-change: transform;

		@media screen and (min-width: 1440px) {
			max-width: 1440px;
			margin: 0 auto;
			position: relative;
		}
	}

	&__cards {
		display: flex;
		flex-flow: row nowrap;
		justify-content: flex-start;
		align-items: center;
		height: 100%;

		position: relative;

		@media screen and (max-width: 1440px) {
			padding-left: 88px;
		}
	}

	&__card {
		width: 480px;
		height: 520px;
		padding: 48px 40px 16px 40px;
		margin-right: 20px;
		flex-shrink: 0;

		position: relative;

		background: #f5f5f5;

		border-radius: 30px;
		overflow: hidden;

		@media screen and (max-width: 991px) {
			padding: 24px;
			width: 380px;
			height: 420px;
		}
	}

	&__card-heading-text {
		font-size: 24px;
		line-height: 32px;
		margin-bottom: 12px;
	}

	&__card-subheading {
		margin-bottom: 40px;
	}

	&__card-heading-text {
		font-size: 24px;
		line-height: 32px;
		margin-bottom: 12px;
	}

	&__card-subheading-text {
		font-family: SamsungOne, sans-serif;
		font-weight: 400;
		font-size: 18px;
		line-height: 27px;
	}

	&__card-heading-text,
	&__card-subheading-text {
		color: $c-black;
	}

	&__card-heading-text {
		font-family: 'Samsung Sharp', sans-serif;
		font-weight: 700;
	}

	&__card-decor {
		position: absolute;
		bottom: -27px;
		left: 0;

		@media screen and (max-width: 991px) {
			bottom: 0px;

			&:not(&:first-child) {
				width: 100%;
				display: flex;
				justify-content: center;
			}
		}
	}

	&__heading {
		margin-bottom: 30px;
		max-width: 1440px;
    margin: 0 auto;
		position: relative;
		top: 15%;
		padding-left: 88px;
	}

	&__heading-text {
		font-size: clamp(34px, 9vw, 48px);
		line-height: 58px;
		color: $c-black;
		font-family: 'Samsung Sharp', sans-serif;
		font-weight: 700;
	}
}

```