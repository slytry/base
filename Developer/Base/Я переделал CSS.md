```
.compromise {
	&__space-holder {
		position: relative;
	}

	&__sticky {
		position: sticky;
		top: 0;
		margin: 0 auto;
		height: 100vh;

		will-change: transform;
		overflow-x: hidden;
	}

	&__heading-wrapper {
		@media screen and (min-width: 1440px) {
			max-width: 1440px;
			margin: 0 auto;
			position: relative;
		}
	}

	&__heading {
		font-size: clamp(34px, 3.3vw, 48px);
		font-family: 'Samsung Sharp', sans-serif;

		padding-top: clamp(48px, 8.34vw, 120px);
		padding-left: 88px;

		@media screen and (max-width: 991px) {
			padding-left: 24px;
		}
	}

	&__horizontal {
		@media screen and (min-width: 1440px) {
			max-width: 1440px;
			margin: 0 auto;
			position: relative;
		}
	}

	&__cards {
		display: flex;
		column-gap: 20px;
		padding-right: 20px;

		padding-top: 60px;
		padding-left: 88px;

		@media screen and (max-width: 991px) {
			padding-left: 24px;
		}
	}

	&__card {
		width: 480px;
		flex-shrink: 0;

		display: flex;
		flex-direction: column;
		justify-content: space-between;

		background: #f5f5f5;

		border-radius: 30px;

		@media screen and (max-width: 991px) {
			width: 270px;
		}
	}

	&__content-wrapper {
		padding: 48px 40px 0 40px;

		@media screen and (max-width: 991px) {
			padding: 24px 24px 0 24px;
		}
	}

	&__card-heading {
		font-family: 'Samsung Sharp', sans-serif;
		font-size: clamp(18px, 2.2vw, 24px);
		margin-bottom: 12px;
	}

	&__card-subheading {
		font-weight: 400;
		font-size: 18px;
		line-height: 1.5;

		@media screen and (max-width: 991px) {
			font-size: 15px;
		}
	}

	&__card-image {
		border-radius: 0 0 30px 30px;
	}
}

```