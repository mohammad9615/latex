# latex\documentclass[12pt, a4paper]{article}
\usepackage{xcolor}
\usepackage{graphicx}%برای تنظیم رنگ هایپرلینک
\usepackage[colorlinks,linkcolor=red,citecolor=blue]{hyperref}
\usepackage{amsthm,amssymb,amsmath,mathrsfs}
\usepackage{tikz-cd}
\makeatletter
\usepackage{booktabs,float}
\newcommand{\rmnum}[1]{\romannumeral #1}
\newcommand{\Rmnum}[1]{\expandafter\@slowromancap\romannumeral #1@}
\makeatother
\usepackage{titlesec}
\usepackage[bottom]{footmisc}
\interfootnotelinepenalty=10000%برای اینکه بتوان پاورقی طولانی داشت بدون شکسته 

\makeatletter
\newcommand*{\Computebaselinestretch}[1]{%
	\strip@pt\dimexpr\number\numexpr\number\dimexpr#1\relax*65536/\number\dimexpr\baselineskip\relax\relax sp\relax
}

\makeatletter
\def\thickhline{%
	\noalign{\ifnum0=`}\fi\hrule \@height \thickarrayrulewidth \futurelet
	\reserved@a\@xthickhline}
\def\@xthickhline{\ifx\reserved@a\thickhline
	\vskip\doublerulesep
	\vskip-\thickarrayrulewidth
	\fi
	\ifnum0=`{\fi}}
\makeatother

\newlength{\thickarrayrulewidth}
\setlength{\thickarrayrulewidth}{3\arrayrulewidth}



\makeatother
\linespread{\Computebaselinestretch{0.5cm}}
\begin{document}
By induction, it is proved that ${\delta }'\left( {{{\text{{q}'}}}_{\text{0}}}\text{,x} \right)\text{=}\left[ {{\text{P}}_{\text{1}}}\text{, }{{\text{P}}_{\text{2}}}\text{,}...\text{,}{{\text{P}}_{\text{k}}} \right]$  if and only if 
\[\delta'(\text{q}_\text{0},\text{x}) =\{\text{P}_\text{1},~ \text{P}_\text{2},~...,~ \text{P}_\text{k}\}\]
So, $\delta'(\delta'(\text{q}_0',x),\text{a})=\delta'(\left[ {{\text{P}}_{\text{1}}}\text{, }{{\text{P}}_{\text{2}}}\text{,}...\text{,}{{\text{P}}_{\text{k}}} \right],\text{a})=[\text{r}_1,~\text{r}_2,...,~\text{r}_k]$ if and only if
\[\delta({\text{P}_1,~\text{P}_2,...,~\text{P}_n},~a)=\delta (\text{P}_1,~\text{a})\cup (\text{P}_2,~\text{a}) \cup ..... \cup (\text{P}_n,~\text{a})\]
\[=\text{r}_1 \cup \text{r}_2 \cup ....\cup \text{r}_\text{k} \]
Thus $\delta'(\text{q}_0'\text{xa})=\delta'(\delta'(\text{q}_0',x)\text{a})==\text{r}_1 \cup \text{r}_2 \cup ....\cup \text{r}_\text{k}$

It is proved that the result is true for a string of length $\text{n+1}$, if it is true for a string of length n. Now $\delta'(\text{q}_0',~\text{x}) \in \text{F}'$ when $\delta(\text{q}_0,~\text{x})$ to a state of Q in F.\\
Therefore, it is proved that L(M) = L(M$'$).
\section{Dead State}
The name dead state was mentioned in Example 3.6 of converting an NFA to an equivalent DFA. Dead state is a state where the control can enter and be confined till the input ended, but there is no way to come out from that state. (The string is dead or finished on entering the state.)

\begin{figure}[h!]
	\begin{center}
		\includegraphics[width=9.0cm]{fig/22}
		\label{fig3}
	\end{center}
\end{figure}

An example for the previous finite automata is shown in Fig. 3.22; from $\text{q}_0$ for input 0, there is a path to go to $\text{q}_1$. But there is no path mentioned from $\text{q}_0$ for input 1. The same thing happens also for $\text{q}_2$ for input 0. Now, let a string 101 be given as input to the FA to test the acceptability of the string by the finite automata.

According to the condition of the acceptability, the first condition, i.e., the string will be totally traversed, is not fulfilled. Obviously, the second condition is also not fulfilled.

We have to decide that the string is not accepted by the finite automata without traversing the string totally!

For making the string totally traversed, we have to 
include an extra state, say $\text{q}_\text{f}$, where the control will go from the states for which there is only one path for one input. In the state $\text{q}_\text{f}$, for the inputs, there will be a self-loop. Here, $\text{q}_\text{f}$ is the dead state.

By including the dead state, the finite automata becomes as shown in Fig. 3.23.

Dead state makes the string totally traversed.


\begin{figure}[H]
	\begin{center}
		\includegraphics[width=9.0cm]{fig/23}
		\label{fig23}
	\end{center}
\end{figure}

\section{Finite Automata with Output}

Till now, we were discussing machines with no output. But two things, output and output relations, are omitted. This was mentioned in the characteristics of the automaton. As FA is a machine, it must produce output. In this section, we shall discuss finite automata with output. Finite automata with output can be divided into two types:
\begin{enumerate}
	\item The Mealy machine
	\item The Moore machine
\end{enumerate}

\subsection{The Mealy Machine}
The Mealy machine was proposed by \textit{George H. Mealyat} the Bell Labs in 1960.

The Mealy machine is one type of finite automata with output, where the output depends on the present state and the present input.

The Mealy machine consists of six touples

\[\text{M=} (\text{Q},\Sigma,\Delta,\delta,\lambda,\text{q}_\text{0} ),\]
where

\begin{itemize}
	\item Q : finite non-empty set of states
	\item $\Sigma$ : set of input alphabets
	\item $\Delta$ : set of output alphabets
	\item $\delta$ : transitional function mapping $\text{Q}\times \Sigma \rightarrow \text{Q}$
	\item $\lambda$ : output function mapping $\text{Q}\times \Sigma \rightarrow \Delta$
	\item $\text{q}_\text{0}$ : beginning state	
\end{itemize}
\subsection{The Moore Machine}
The Moore machine was proposed by \textit{Edward F. Moorein} IBM around 1960.

The Moore machine is one type of finite automata where output depends on the present state only, but the output is independent of the present input.

The Moore machine consists of six touples
\[\text{M=} (\text{Q},\Sigma,\Delta,\delta,\lambda,\text{q}_\text{0} ),\]

\begin{itemize}
	\item Q : finite non-empty set of states
	\item $\Sigma$ : set of input alphabets
	\item $\Delta$ : set of output alphabets
	\item $\delta$ : transitional function mapping $\text{Q}\times \Sigma \rightarrow \text{Q}$
	\item $\lambda$ : output function mapping $\text{Q} \rightarrow \Delta$
	\item $\text{q}_\text{0}$ : beginning state	
\end{itemize}

\subsection{Tabular and Transitional Representation of the Mealy and Moore Machines}

\subsubsection{Tabular}
The output of the Mealy machine depends on both the present state and the present input. So, for the mealy machine, there will be n number of output columns if there are n number of input.

The tabular format of the Mealy machine is as follows.

\begin{table}[]
	\centering
	\begin{tabular}{ccccccc}
		\thickhline
		& & \multicolumn{2}{c}{I/P=0} & & \multicolumn{2}{c}{I/P=1} \\ \cline{3-4} \cline{6-7}
		Present State & & Next State      & O/P   &  & Next State      & O/P     \\ \hline
		A             & & D               & 0     &  & B               & 0       \\
		B             & & A               & 1     &  & D               & 0       \\
		C             & & B               & 1     &  & A               & 1       \\
		D             & & D               & 1     &  & C               & 0       \\ \thickhline
	\end{tabular}
\end{table}
The output of the Moore machine depends on the present state only. As in a machine, there is only one present state column, so there is only one output column. 

The tabular format of the Moore machine is given in the following table.
\begin{table}[]
	\centering
	\begin{tabular}{cccccc}
		\thickhline
		& & \multicolumn{2}{c}{Next State} & &  \\ \cline{2-4} 
		Present State & & {I/P=0}      & {I/P=1}   &   & O/P     \\ \hline
		A             & & A               & B     &  & 0                      \\
		B             & & A               & C     &  & 0                      \\
		C             & & A               & C     &  & 1                      \\ \thickhline
	\end{tabular}
\end{table}

\subsubsection{Transitional}
The Mealy machine is one type of finite automata with output. The transitional diagram is like finite automata, but the output is mentioned. As we know, the output of a Mealy machine depends on the pres-ent state and the present input. So, for a Mealy machine, the transitional arc will be labelled with both input and output like the example in Fig. 3.24.

\begin{figure}[H]
	\centering
	\begin{center}
		\includegraphics[width=9.0cm]{fig/24}
		\label{fig4}
	\end{center}
\end{figure}

The output of the Moore machine depends only on the present state. For a Moore machine, the states are 
labelled with the state name and the output like the example shown in Fig. 3.25.

\begin{figure}[H]
	\begin{center}
		\includegraphics[width=9.0cm]{fig/25}
		\label{fig5}
	\end{center}
\end{figure}
The following are some examples of finite automata with output.

\textbf{Example 3.10} Design a Mealy machine to get complement of binary number.

\textbf{Solution:} For input 0, the machine gives the output 1, and for input 1 the machine will give the output 0. The Mealy machine is constructed as shown in Fig. 3.26.
\begin{figure}[H]
	\begin{center}
		\includegraphics[width=3.0cm]{fig/26}
		\label{fig26}
	\end{center}
\end{figure}

\textbf{Example 3.11} Design a Moore machine which determines the residue mod-3 for each binary string treated as binary integer.

\textbf{Solution:}
Binary string consists of two types of characters 0 and 1. Binary integer means the decimal equivalent of a binary string as integer number. Residue mod-3 means the reminder received when the decimal equivalent of the binary number is divided by 3.

If a decimal number is divided by 3, only three types of reminders 0 or 1 or 2 are generated. The out-put of the Moore machine depends only on the present state. So, for three types of reminders (output), three states are needed.

Let us assume that state $\text{q}_0$ is producing output 0, state $\text{q}_1$
is producing output 1, and state $\text{q}_2$ is producing output 2. Now, it is needed to construct the transitional arcs. Before construction, take a table containing binary equivalent of decimal numbers from 0 to 9 and the reminders for each of them, when divided by 3.

\begin{table}[h]
	\centering
	\begin{tabular}{ccc}
		\thickhline
		Decimal &Binary &Reminders  \\ \toprule 
		 0             &0             &0          \\ \hline
	     1             &1             &1          \\
		 2             &10             &2          \\      
		 3             &11             & 0        \\
		 4             &100             &1          \\
		 5             &101             & 2         \\                            
		 6             &110             &0          \\
		 7             & 111            &1          \\
		 8             &1000             &  2        \\		              
		 9             &1001             &  0      \\	\thickhline
	\end{tabular}
\end{table}

\end{document}
