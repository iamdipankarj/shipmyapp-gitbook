---
description: >-
  Lets setup emails for our app. Collect emails, send transactional emails,
  welcome emails and more.
---

# 📧 Emails

ShipMyApp uses [Resend](https://resend.com/) **for** handling emails.

1. Head over to [https://resend.com/](https://resend.com/) and create an account.
2. Once you setup your account and add a domain, you will receive an API key in their dashboard,
3. Once you obtain your API key, paste it to `.env` file as shown in [environment-variables.md](environment-variables.md "mention")

{% code title="" %}
```
RESEND_API_KEY=
```
{% endcode %}

4. Email templates and hooks are hanldled in `src/emails` folder.
5. Example Email to send magic links.

```typescript
export async function sendMagicLink(params: {
  identifier: string
  url: string
}) {
  const { identifier, url } = params
  const { host } = new URL(url)

  try {
    const data = await resend.emails.send({
      from: 'no-reply@notification.shipmyapp.com',
      to: [identifier],
      subject: `Log in to ${host}`,
      text: text({ url, host }),
      react: MagicLinkEmail({ url, host })
    })
    return { success: true, data }
  } catch (error) {
    throw new Error('Failed to send the verification Email.')
  }
}
```

6. Example Welcome Email.

```tsx
export const WelcomeEmail = ({
  userFirstname,
}: WelcomeEmailProps) => (
  <Html>
    <Head />
    <Preview>
      The sales intelligence platform that helps you uncover qualified leads.
    </Preview>
    <Body style={main}>
      <Container style={container}>
        <Img
          src={`${baseUrl}/icon-colored.png`}
          width="100"
          height="100"
          alt="ShipMyApp"
          style={logo}
        />
        <Text style={paragraph}>Hi {userFirstname},</Text>
        <Text style={paragraph}>
          Welcome to ShipMyApp, the NextJS boilerplate for startups.
        </Text>
        <Section style={btnContainer}>
          <Button style={button} href="https://shipmyapp.com">
            Get started
          </Button>
        </Section>
        <Text style={paragraph}>
          Best,
          <br />
          The ShipMyApp team
        </Text>
        <Hr style={hr} />
        <Text style={footer}>
          470 Noor Ave STE B #1148, South San Francisco, CA 94080
        </Text>
      </Container>
    </Body>
  </Html>
);
```

7. An example of how to send emails as defined in `src/app/api/auth/[...next-auth]/route.ts`

```typescript
sendWelcomeEmail({
  identifier: user.email!,
  url: process.env.NEXTAUTH_URL!,
  userFirstname: user.name!
});
```

