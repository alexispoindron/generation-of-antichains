A. Karzanov and L. Khachiyan. From the paper of Karzanov and Khachiyan, an algorithm to generate random linear extensions

antichains1.txt to antichains5.txt: exhaustive lists of antichains of the power set of size 1 to 5
general_all_antichains_power_set: the code that generates antichains1.txt to antichains5.txt

total_tension: generation of antichains using the maximal tension (=jump) criterion
\subsection{Method 9. The maximal jump criterion with constant step values}
\begin{algorithm} 
  \caption{$9^{th}$ method. The maximal jump criterion}
 \begin{algorithmic}
 \State{Generate a linear extension and its induced rank function.}
 \State{Calculate the jump at each state.}
 \State{Arrange the states according to their jump, in decreasing order; we get list $ \mathcal{L}$}
 \State{flag=0}
 \State{$\cA:=\emptyset$}
 \While{flag$\neq $ 1}
\State{Check if the next element of $ \mathcal{L}$ can be added to $ \mathcal{A}$ and continue until an element is found that cannot}
\State{When this is the case, set flag=$ 1$}
 \EndWhile
\end{algorithmic}
  % \begin{algorithmic}[1]
  % %  \EndFor
  % \end{algorithmic}
  \label{algo11}
\end{algorithm}
\subsection{Method 9. bis. The maximal jump criterion with random step values}
\begin{algorithm} 
  \caption{$9.bis^{th}$ method. The maximal jump criterion}
 \begin{algorithmic}
 \State{Generate a linear extension.}
 \State{Generate increasing values in [0,1] on the total order}
 \State{Calculate the jump at each state.}
 \State{Arrange the states according to their jump, in decreasing order; we get list $ \mathcal{L}$}
 \State{flag=0}
 \State{$\cA:=\emptyset$}
 \While{flag$\neq $ 1}
\State{Check if the next element of $ \mathcal{L}$ can be added to $ \mathcal{A}$ and continue until an element is found that cannot}
\State{When this is the case, set flag=$ 1$}
 \EndWhile
\end{algorithmic}
  % \begin{algorithmic}[1]
  % %  \EndFor
  % \end{algorithmic}
  \label{algo11}
\end{algorithm}



max jump with random values
\begin{algorithm} 
  \caption{$9^{th}$ method. The maximal jump criterion}
 \begin{algorithmic}
 \State{Generate a linear extension and its induced rank function.}
 \State{Calculate the jump at each state.}
 \State{Arrange the states according to their jump, in decreasing order; we get list $ \mathcal{L}$}
 \State{flag=0}
 \State{$\cA:=\emptyset$}
 \While{flag$\neq $ 1}
\State{Check if the next element of $ \mathcal{L}$ can be added to $ \mathcal{A}$ and continue until an element is found that cannot}
\State{When this is the case, set flag=$ 1$}
 \EndWhile
\end{algorithmic}
  \label{algo11}
\end{algorithm}

relabelling method: method of random generation where we apply a relabelling at each step
\begin{algorithm} 
  \caption{Second method. Instance: number of experiments (T) and the batch size (b)}
  \begin{algorithmic}
\State{Start with an antichain $ \cA_0$}
\For{ T experiments}
\State{Add $b$ random states}
\State{Apply a relabelling on all states ($S\leftarrow S\Delta B$ for some random $B$)}
\While{ the resulting collection is not an antichain}
\State{Remove one state among the ones that dominate or that are dominated by the largest number of states}
\EndWhile
\EndFor
\end{algorithmic}
  \label{algo2}
\end{algorithm}

stratification algo 5: extract layers in the spirit of the Dilworth theorem
\begin{algorithm} 
  \caption{Fifth method: stratification}
  \begin{algorithmic}
  \State{Generate a capacity (either with constant step, or random distribution of values)}
  \State{Partition the linear extension into antichains $\cA_0=\{S_0, S_1 \ldots, S_{k_1}\} $, $ \cA_1=\{S_{k_1+1}, \ldots, S_{k_2}$, $ \ldots$, $ \cA_{K}=\{S_{k_K+1}, \ldots, S_{2^n-2}\}$.}
\end{algorithmic}
  \label{algo5}
\end{algorithm}

(upcoming algorithms; not available yet)
\begin{algorithm} 
  \caption{Third method. Random nodes generator Instance: number of experiments (T)}
  \begin{algorithmic}
  \State{$\mathcal{F}:=2^N$}
  \State{$F_0:=\emptyset$ and $ F_1:=\emptyset$}
\While{$\mathcal{F}\neq \emptyset$}
\State{Pick a random state $S\in \mathcal{F}$}
\State{With probability $1/2$, $ F_0\leftarrow F_0\cup \bigcup_{T \in F_0} [[S,T]]\setminus F_1$ and $ \mathcal{F} \leftarrow \mathcal{F} \setminus  [\emptyset , S] $. With probability $1/2$, $ F_1\leftarrow \bigcup_{T \in F_1} [[S,T]]\setminus F_0$ and $ \mathcal{F} \leftarrow \mathcal{F} \setminus  [S,N] $.}
\EndWhile
\State{Apply the algorith of \citet{unate} to find the signs $ \Sigma $ of the unate function corresponding to $(F_0,F_1)$}
\State{Relabel all vectors with the transformation $ S\leftarrow S\Delta \overline{\Sigma}$}
\State{Extract the antichain}
\end{algorithmic}
  \label{algo3}
\end{algorithm}


\begin{algorithm} 
  \caption{Tenth method. Random nodes generator Instance: number of experiments (T)}
 \begin{algorithmic}
  \State{$\mathcal{F}:=2^N$}
  \State{$F_0:=\emptyset$ and $ F_1:=\emptyset$}
\While{$\mathcal{F}\neq \emptyset$}
\State{Pick a random state $S\in \mathcal{F}$}
\State{With probability $1/2$, $ F_0\leftarrow F_0\cup [\emptyset , S]$ and $ \mathcal{F} \leftarrow  \mathcal{F}  \setminus  [\emptyset , S] $. With probability $1/2$, $ F_1\leftarrow F_1\cup [S,N]$ and $ \mathcal{F} \leftarrow \mathcal{F}  \setminus  [S,N] $.}
\EndWhile
\State{Apply the algorith of \citet{unate} to find the signs $ \Sigma $ of the unate function}
\State{Relabel all vectors with the transformation $ S\leftarrow S\Delta \overline{\Sigma}$}
\State{Extract the antichain}
\end{algorithmic}
  % \begin{algorithmic}[1]
  % %  \EndFor
  % \end{algorithmic}
  \label{algo10}
\end{algorithm}

\begin{algorithm} 
  \caption{$11^{th}$ method. Random nodes generator Instance: number of experiments (T)}
 \begin{algorithmic}
  \State{$\mathcal{F}:=2^N$}
  \State{$F_0:=\emptyset$ and $ F_1:=\emptyset$}
  \State{time=0}
\While{$\mathcal{F}\neq \emptyset$}
\State{time+=1}
\State{Pick a random state $S$  (not necessarily in $\mathcal{F}$) according to a distribution $ P^{time}(k)$ where $ P^{time+1}(k)$ first order stochastically dominate $ P^{time}(k)$.}
\If{$S\notin F_1$}
\State{$ F_0\leftarrow F_0\cup [\emptyset , S]$}
\EndIf

\State{Pick a random state $T$  (not necessarily in $\mathcal{F}$) according to a distribution $ n-P^{time}(k)$ where $ P^{time+1}(k)$ first order stochastically dominate $ P^{time}(k)$.}
\If{$S\notin F_0$}
\State{$ F_1\leftarrow F_1\cup [T,N]$}
\EndIf
\EndWhile
\State{Extract the antichain}
\end{algorithmic}
  % \begin{algorithmic}[1]
  % %  \EndFor
  % \end{algorithmic}
  \label{algo11}
\end{algorithm}



\begin{algorithm}
  \caption{Method 6}
  \begin{algorithmic}
\State{$A=\emptyset$ (will be our list of antichains)}
    \For{$t=1..T$}
      \State Generate linear extensions. Call them $L_{i}^{t}$ for $i=1..2^n$.
          \EndFor
      \State{$(a,b)=(1,1)$}
      \While{Not all linear extensions are partitioned into antichains.}
        \State Start a new antichain $\cA=\emptyset$  at $(i,t)=(a,b) $ (corner node).
        \State Start from $L_i^{t}$ where $i,t$ are as small as possible.
        \If{possible include $L_i^{t+1}$ into the antichain.}
          \State Continue
        \Else
          \If{possible include $L_{i+1}^{t}$ into the antichain.}
            \State Continue
          \Else
            \If{possible include $L_{i+1}^{t+1}$ into the antichain}
              \State Continue
            \Else
              \State{This antichain $\cA$ is finished.}
              \If{$ \cA\notin A$}
              \State{$A=A\cup \{\cA\}$}
              \EndIf
            \EndIf
          \EndIf
        \EndIf
        \State{$(a,b)=(i,t+1)$ where $ t  $ is taken modulo $ T$ and $ (i,t+1) $ as small as possible} 
      \EndWhile
  \end{algorithmic}
  \label{algo6}
\end{algorithm}
