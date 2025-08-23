package com.board.controller;

import com.board.model.Board;
import com.board.repository.BoardRepository;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController
@RequestMapping("/api/boards")
public class BoardController {

    private final BoardRepository boardRepository;

    public BoardController(BoardRepository boardRepository) {
        this.boardRepository = boardRepository;
    }

    @GetMapping
    public List<Board> getAllBoards() {
        return boardRepository.findAll();
    }

    @GetMapping("/{id}")
    public ResponseEntity<Board> getBoardById(@PathVariable Long id) {
        return boardRepository.findById(id)
                .map(ResponseEntity::ok)
                .orElse(ResponseEntity.notFound().build());
    }

    @PostMapping
    public Board createBoard(@RequestBody Board board) {
        return boardRepository.save(board);
    }

    @PutMapping("/{id}")
    public ResponseEntity<Board> updateBoard(@PathVariable Long id, @RequestBody Board boardDetails) {
        return boardRepository.findById(id).map(board -> {
            board.setTitle(boardDetails.getTitle());
            board.setDescription(boardDetails.getDescription());
            return ResponseEntity.ok(boardRepository.save(board));
        }).orElse(ResponseEntity.notFound().build());
    }

    @DeleteMapping("/{id}")
    public ResponseEntity<Void> deleteBoard(@PathVariable Long id) {
        return boardRepository.findById(id).map(board -> {
            boardRepository.delete(board);
            return ResponseEntity.noContent().<Void>build();
        }).orElse(ResponseEntity.notFound().build());
    }
}
