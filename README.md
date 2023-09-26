## Next.js playground

- [공식문서](https://nextjs.org/docs) 뽀개기👊
- [FAQ](https://nextjs.org/docs/app#frequently-asked-questions)

<br>

## Docs

### 🍋 App Router vs Pages Router

**`Next.js`** 는 두 개의 router가 있다. **`Next.js`** 는 file-system routing을 사용한다. 즉, 파일 구조에 따라 router가 결정된다. 같은 프로젝트 내에서 두 종류의 router를 함께 사용할 수 있다.

- **`App Router(recommend)`** : 더 최신 버전의 router이다. 리액트의 최신 기능까지 사용할 수 있다. `create-next-app`을 통해 프로젝트를 시작한 경우, App Router를 사용하는 구조로 시작된다.

  - `app/` 폴더를 만들고, `layout.tsx`, `page.tsx` 파일을 추가한다. 어플리케이션의 `/`에 접근하였을 때, 이들이 render된다.

  - `app/layout.tsx` 안엔 `<html>` and `<body>` 태그가 필요하다.

    ```tsx
    // app/layout.tsx

    export default function RootLayout({
      children,
    }: {
      children: React.ReactNode;
    }) {
      return (
        <html lang="en">
          <body>{children}</body>
        </html>
      );
    }
    ```

    ```tsx
    // app/page.tsx

    export default function Page() {
      return <h1>Hello, Next.js!</h1>;
    }
    ```

- **`Page Router`** : 기존 **`Next.js`** 의 router이다.

  - 프로젝트 `root`에 ` pages`` 폴더를 만들고(optional)  `index.tsx`를 만든다. 이 파일이 home(`/`)페이지가 된다.

    ```tsx
    // pages/index.tsx

    export default function Page() {
      return <h1>Hello, Next.js!</h1>;
    }
    ```

  - 그리고 `pages/` 안에 `_app.tsx` 파일을 만들어 global layout을 정의해준다.

    ```tsx
    import type { AppProps } from "next/app";

    export default function App({ Component, pageProps }: AppProps) {
      return <Component {...pageProps} />;
    }
    ```

  - 마지막으로, `pages/` 안에 `_document.tsx`를 만들어, 서버에 줄 초기 페이지(응답)을 만들어 준다.

    ```tsx
    import { Html, Head, Main, NextScript } from "next/document";

    export default function Document() {
      return (
        <Html>
          <Head />
          <body>
            <Main />
            <NextScript />
          </body>
        </Html>
      );
    }
    ```

<br>

### 🍋 Next.js Project Structure

<br>

## Getting Started

This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

<br>

First, run the development server:

```bash
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

<br>
